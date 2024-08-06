# Documentation

## Variables

| Column | Description | Type | Changes | Questions |
|-|-|-|-|-|
| material | Unique code for each product. | nominal |- Alter name<br>- int -> string ||
| descricao_material | Product name. | nominal | - Alter name ||
| gm3 | Merchandise category code to which each product belongs. | nominal | - int -> string ||
| descricao_gm3 | Merchandise category name. | nominal | - Alter name ||
| id_loja | Code of the shop where the sale was made.| nominal | - Alter name<br>- int -> string ||
| nome_loja | Name of the shop where the sale was made. | nominal | - Alter name ||
| cidade_loja | City of origin of the shop. | nominal | - Alter name ||
| uf | State of origin of the shop. | nominal | - Alter name<br>- amazonas -> AM ||
| preco_custo | Cost price (excluding shipping) of the product. | continuous | - Alter name ||
| frete | Percentage of the shipping price that must be applied to the cost price to obtain the total cost price of the product. | continuous | - Alter name<br>- string -> int<br>- Delete '%'<br>- NaN -> 0.0 | - What is the business rule for defining shipping?<br> - 0.73 only for Eletrolux products? |
| preco_venda | Selling price of the product. | continuous | - Alter name | - What is the rule for calculating the sales price?<br> - Why do some products have such a big difference in preco_custo? |
| qtd_vendida | Number of units sold on a given date. | discrete | - Alter name ||
| data_venda | Day of sale. | date | - Alter name<br>- string -> date |
| dia_semanal | Weekday. | nominal |||
| valor_frete | preco_custo * frete <br>- shipping calculation  | continuous || - Is the shipping cost included in "cost_price" or "sale_price"? |
| preco_custo_total | preco_custo + valor_frete | continuous | | - 20k tv with 0 shipping?|
| receita | preco_venda * qtd_vendida | continuous |||
| custo | preco_custo_total * qtd_vendida | continuous |||
| margem_lucro_financeira | receita - custo | continuous |||
| margem_lucro_percentual | (margem_lucro_financeira / receita) * 100 | continuous |||

## Notes

* The dataframe has 50229 rows and 20 columns.

* Period: 01/05/2020 - 30/04/2024.

* Set values with only 2 decimal places.

* Extreme values of 'preco_venda' > 10000 have been excluded.

