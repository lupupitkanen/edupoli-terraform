# Edupoli Terraform-harjoitus

Harjoitellaan terraform infra-automaatiota perustamalla virtuaalipalvelin Google Cloud Platform -alustalle Haminaan ja osoittamalla verkkotunnus siihen Cloudflaren avulla.

## Kloonaa harjoitusprojekti

```
cd
mkdir projects
cd projects
git clone git@github.com:lupupitkanen/edupoli-terraform.git
cd edupoli-terraform
git init
```

## Muuttujat

- project_name: Valitsemasi nimi projektille Google Cloud Platformissa
- billing_account: [Google Cloud Console](https://console.cloud.google.com/) -> Billing -> Billing account ID
- cloudflare_email: Cloudflare-tilin sähköpostiosoitteesi
- cloudflare_token: [Cloudflare](https://dash.cloudflare.com/) -> My Profile -> API Keys -> Global API Key
- cloudflare_domain: Oma domain nimesi, esim. sinundomain.tk

### Tiedostoon terraform.tfvars

```
project_name = ""
billing_account = ""
cloudflare_email = ""
cloudflare_token = ""
cloudflare_domain = ""
```

### Tai ympäristömuuttujina komentorivillä

```
export TF_VAR_project_name=
export TF_VAR_billing_account=
export TF_VAR_cloudflare_email=
export TF_VAR_cloudflare_token=
export TF_VAR_cloudflare_domain=
```

## Google Cloud Platform kirjautuminen

```
gcloud auth application-default login
```

## Terraform komennot
```
terraform init
terraform plan
terraform apply
```

Testaa aukeaako selaimella omalla domainillasi nginx web-palvelimen oletussivu.

### Lisäkomentoja
```
# Katso outputit
terraform output

# Kirjaudu palvelimelle
ssh <ip-osoite>

# Vaihda palvelimen tyyppi/koko
export TF_VAR_machine_type=n1-standard-2
terraform plan
terraform apply

# POISTA KAIKKI
terraform destroy

# Luo uudlleen puhtaalta pöydältä

terraform plan
terraform apply
```

### Perusta oma projekti GitHubiin

https://github.com/new

```
git add .
git commit -m "first commit"
git remote add origin git@github.com:omanimi/omaprojekti.git
git push -u origin master
```

Huomaa oma tunnus ja valitsemasi projektin nimi!
