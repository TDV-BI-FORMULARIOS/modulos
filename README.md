# Modulos dos formularios

Biblioteca compartilhada pelos formularios em Streamlit do B.I.

```
pip install git+https://github.com/TDV-BI-FORMULARIOS/modulos.git@main
```

```python
from Modulos import ConectionSupaBase
from Modulos import AzureLogin
import Modulos.Minio.examples.MinIO as meu_minio
```

## O repositorio e publico. Por que

O `pip` do Streamlit Cloud nao autentica em dependencia privada: as chaves de
deploy dao acesso ao repositorio **da aplicacao**, nao as dependencias dela.

Por isso aqui so entra codigo que nao guarda segredo nenhum. Os tres modulos
leem credencial de `st.secrets` (Streamlit) ou de variavel de ambiente, que
vivem na configuracao de cada aplicacao - nunca neste repositorio.

**Nenhum `.env` pode ser commitado aqui.**

## Configuracao esperada em cada formulario

| modulo | chaves |
|---|---|
| `ConectionSupaBase` | `SUPABASE_URL`, `SUPABASE_KEY` |
| `AzureLogin` | `AZURE_CLIENT_ID`, `AZURE_CLIENT_SECRET`, `AZURE_REDIRECT_URI`, `AZURE_AUTH_URL`, `AZURE_TOKEN_URL` |
| `Minio` | `MINIO_ENDPOINT`, `MINIO_ACCESS_KEY`, `MINIO_SECRET_KEY`, `MINIO_SECURE` |

## Historico

Substitui o `DellaVolpe69/Modulos`, que ficava numa conta pessoal e tinha dois
`.env` com credenciais do MinIO versionados.
