SELECT

    purchase_date,
    purchase_id,
    pur.client_id AS client_id,
    dateDiff('year', cli.birth_date, toDate(now())) AS client_age,
    dateDiff('month', cli.registration, toDate(now())) AS client_registration_age,
    promotion_name,
    category_name,
    partner_name,
    pur.city_id AS city_id,
    cty.city AS city,
    cli.client_city_id AS client_city_id,
    client_city ,
    client_category,
    revenue,
    quantity

FROM
    (
    SELECT  purchase_date, purchase_id, client_id, promotion_id, city_id,
            CASE
                WHEN client_id IN
                (
                SELECT
                client_id
                FROM
                  (
                    SELECT
                    client_id ,
                    COUNT(purchase_id) AS sum_p
                    FROM project_variant_2.purchase
                    GROUP BY purchase.client_id
                    HAVING sum_p <= 1
                    )
                ) THEN 'new'
                ELSE 'old'
            END AS client_category,
            price * quantity AS revenue, quantity AS quantity
    FROM project_variant_2.purchase
    WHERE (purchase_date BETWEEN '2020-05-01' AND '2020-08-01') AND status == 1
    GROUP BY client_id, purchase_id, purchase_date, promotion_id, city_id, revenue, quantity
    ) AS pur

    LEFT JOIN project_variant_2.client AS cli 
            ON pur.client_id = cli.client_id
    LEFT JOIN project_variant_2.promotion AS pro 
            ON pur.promotion_id = pro.promotion_id 
    LEFT JOIN ( SELECT DISTINCT city_id,  city FROM city ) AS cty 
            ON pur.city_id   = cty.city_id
    LEFT JOIN ( SELECT DISTINCT  client_city_id,  client_city  FROM city ) AS cty_cli 
            ON cli.client_city_id = cty_cli.client_city_id 
