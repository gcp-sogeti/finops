## Reporting

----

### Billing dans bigquery
* Les informations liées au billing sont **exportées en continu dans Bigquery**.
	* Table détaillée des coûts journalier:
    > **gcp_billing_export_v1_<BILLING_ACCOUNT_ID>**
	* Grille tarifaire:
    > **cloud_pricing_export**
	

----

## Requetes dans bigquery
```sql
SELECT
  invoice.month, service.description,
  ROUND(SUM(cost) + SUM(IFNULL((
        SELECT
          SUM(c.amount)
        FROM
          UNNEST(credits) c),
        0))) AS cost_after_credits
FROM
  `data-analytics-pocs:public.gcp_billing_export_EXAMPL_E0XD3A_DB33F1`
WHERE
  invoice.month = "201906"
GROUP BY
  1,2
ORDER BY 3 DESC;
```

----

## Resultat de la requete bigquery


<table>
<tr><td>Row</td><td>Month</td><td>Description</td><td>cost_after_credits</td></tr>
<tr><td>----</td><td>----</td><td>----</td><td>----</td></tr>
<tr><td>1</td><td>201906</td><td>Compute engine</td><td>$1605.0</td></tr>
<tr><td>2</td><td>201906</td><td>Cloud Storage</td><td>$10.5</td></tr>
<tr><td>3</td><td>201906</td><td>App Engine</td><td>$1220.0</td></tr>
<tr><td>4</td><td>201906</td><td>Cloud Pub/Sub</td><td>$0.0</td></tr>
</table>


----

## Visualiser les dépenses avec Google Data Sutdio

Google propose des templates permettant de suivre depuis Google Data Studio les dépenses
![DataStudio](img/Billing-dashboard.png)