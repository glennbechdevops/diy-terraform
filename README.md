# Fix it yourself lab

Du skal gjøre denne laben i GitHub Codespaces. Codespaces gir deg et fullstendig utviklingsmiljø i nettleseren med alt du trenger ferdig installert.

## Oppsett av Codespaces

1. Gå til dette repositoryet på GitHub
2. Klikk på den grønne **Code**-knappen
3. Velg **Codespaces**-fanen
4. Klikk **Create codespace on main**
5. Vent mens Codespaces starter opp (tar vanligvis 1-2 minutter)

Codespaces kommer med AWS CLI og Terraform ferdig installert.

## Konfigurere AWS credentials

Når Codespaces er startet, må du konfigurere dine AWS credentials:

```bash
aws configure
```

Du vil bli spurt om:
- AWS Access Key ID
- AWS Secret Access Key
- Default region name (bruk `eu-west-1`)
- Default output format (trykk bare Enter)

## Beskrivelse 

Lambdafunksjonen i dette repositoryiet kan ikke deployes og virker ikke av et par årsaker.

* Rollenavn er hardkodet, det finnes rolle med samme navn fra før.
* Lambdafunksjonen sin Rolle gir ikke tilgang til S3 
* Navnet til lambdafunksjonen er hardkodet.
* Funksjonen (koden) forventer å finne en environment variabel som heter ```BUCKET_NAME```     
```
bucket_name = os.environ['BUCKET_NAME'] 
```
* Les dokumentasjonen til aws_lambda_function resource, og finn ut av hvordan du kan sende inn en "environment" variabel til lambda-funksjonen siden den forventer det.
  https://registry.terraform.io/providers/hashicorp/aws/latest/docs/resources/lambda_function.html

## Oppgave

Få koden til å kjøre, og forbedre koden ved å innføre Terraform variabler.





