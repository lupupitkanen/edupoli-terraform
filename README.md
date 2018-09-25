### Google Cloud Platform kirjautuminen

```
gcloud auth application-default login
```

### Muuttujat tiedostoon terraform.tfvars

```
project_name = "eduterra"
billing_account = "01DA9D-28A34C-A62045"
cloudflare_email = "lupu.pitkanen@gmail.com"
cloudflare_token = "a06cbcd86993a96bf88684b0c8f0f8ac031aa"
cloudflare_domain = "luputestaa3.tk"
```

### Tai ympäristömuuttujina komentorivillä

```
export TF_VAR_project_name=
export TF_VAR_billing_account=
export TF_VAR_cloudflare_email=
export TF_VAR_cloudflare_token=
export cloudflare_domain=
```
