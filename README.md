# Calculadora de Imposto

🚀 **Calculadora de Imposto** é um projeto desenvolvido como parte do curso #HoraDeCodar. Este projeto fornece uma interface intuitiva para calcular impostos com base em dados mocados e entradas do usuário.

## Funcionalidades

- 🧾 **Cálculo de Impostos**: Calculo do imposto com base na entrada de valor.
- 📈 **Resultados**: Veja os resultados dos cálculos ao calcular.
- 🔄 **Validação de Entradas**: Utilize validação de formulários para garantir que os dados inseridos são válidos.
- 🎨 **Interface Amigável**: Interface de usuário limpa e fácil de usar, desenvolvida com ReactJS e Material-UI.

## Tecnologias Utilizadas

- **Frontend**: ReactJS
- **Estilo**: Material-UI, Emotion
- **Validação de Formulários**: Formik, Yup

## Instalação e Uso

Para rodar o projeto localmente, siga os passos abaixo:

1. Clone o repositório (somente leitura):
   ```sh
   git clone https://github.com/JefsonOliveira/calculadora_de_imposto.git
   ```
2. Navegue até o diretório do projeto:
   ```sh
   cd calculadora_de_imposto
   ```
3. Instale as dependências:
   ```sh
   npm install formik yup @mui/material @emotion/react @emotion/styled
   ```
4. Inicie o servidor de desenvolvimento com Vite:
   ```sh
   npm run dev
   ```
   O aplicativo estará disponível em http://localhost:3000.

## Exemplo de Uso

```javascript
import React from "react";
import { Formik, Form, Field, ErrorMessage } from "formik";
import * as Yup from "yup";
import { Button, TextField } from "@mui/material";

const TaxCalculator = () => {
  const validationSchema = Yup.object({
    income: Yup.number().required("Required").positive("Must be positive"),
    deductions: Yup.number().required("Required").min(0, "Cannot be negative"),
  });

  return (
    <Formik
      initialValues={{ income: "", deductions: "" }}
      validationSchema={validationSchema}
      onSubmit={(values) => {
        const tax = (values.income - values.deductions) * 0.25;
        alert(`Your tax is: $${tax}`);
      }}
    >
      {({ handleChange, handleBlur, values }) => (
        <Form>
          <div>
            <TextField
              name="income"
              label="Income"
              value={values.income}
              onChange={handleChange}
              onBlur={handleBlur}
            />
            <ErrorMessage name="income" component="div" />
          </div>
          <div>
            <TextField
              name="deductions"
              label="Deductions"
              value={values.deductions}
              onChange={handleChange}
              onBlur={handleBlur}
            />
            <ErrorMessage name="deductions" component="div" />
          </div>
          <Button type="submit">Calculate</Button>
        </Form>
      )}
    </Formik>
  );
};

export default TaxCalculator;
```

Contato
Para dúvidas ou mais informações, entre em contato:

- Nome: Jefson K Oliveira
- Email: kaironoliveira16@gmail.com
- LinkedIn: [Meu Perfil](https://www.linkedin.com/in/jefson-oliveira-a92a62206/)
