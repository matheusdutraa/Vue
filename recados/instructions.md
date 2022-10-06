## ÚTEIS
### Instalar Axios

```
npm install axios
```

## Obter dados de uma API

```
axios.get({URL}).then((response) => {
  console.log(response.data)
}).catch((error) => {
  console.log(error);
});
```

## Enviar dados para uma API

```
axios.post({URL}, DADO_A_SER_ENVIADO).then( (response) => {
    console.log(response);
    this.listar();
}).catch((error) => {
    console.log(error);
});
```
