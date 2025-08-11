# Validación de uso dinámico de entornos de GitHub

## Prerequisitos

Debe existir en el repositorio de github, como mínimo, 2 entornos (environments):
- `test`
- `prod`

## Configuración del repositorio

En cada environment se debe establecer un secreto y una variable de entorno:

- **Secreto**
  - DEPLOYMENT_SECRET: Este secreto debe contener un valor único para cada environment. Por ejemplo:
    - En el environment `test`, el secreto podría ser `test-secret-value`.
    - En el environment `prod`, el secreto podría ser `prod-secret-value`.
- **Variable de entorno**
  - DEPLOYMENT_VAR: Esta variable debe contener el nombre del environment. Por ejemplo:
    - En el environment `test`, la variable podría ser `test`.
    - En el environment `prod`, la variable podría ser `prod`.

## Configuración del workflow

Para validar esta configuración, es necesario que el fichero `dynamic_github_environments/environment` contenga el valor 
del entorno que se quiera usar, según el ejemplo anterior: `test` o `prod`.