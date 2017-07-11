# Celery

## Install 

pip install celery

## test install

* make tasks.py file:

## Example task for testing purposes

`from celery import Celery`

`app = Celery('tasks', broker='amqp://guest@localhost//')`

`@app.task`
`def add(x, y):`
    `return x + y`


inside the directory where you created the tasks.py file run 
`celery -A tasks  worker -l info`

## Specific app example:
running local 

* python manage.py celeryd sap_reports_management worker   -l info
* python manage.py celery worker -E --loglevel=INFO -Q schedule --concurrency=2 -n schedule
* python manage.py celery worker --loglevel=INFO --queues=bigtasks,ipm,helpdesk,cpos,cpos_oi,cpos_claro,cpos_tim,cpos_algar,flowbot,nota_fiscal,nota_fiscal_oi,nota_fiscal_oi_portal,nota_fiscal_tim,nota_fiscal_claro,nota_fiscal_claro_hardware_software,data_importer,schedule,cria,ttt,ipm_sync,portal_tim_folha_servico,nota_fiscal_tim_portal,nota_fiscal_cancelled_tim_portal,claro_delivery,notification_emai
