# automacao-resposta-email-N8N
Esse projeto foi desenvolvido para o aprendizado da ferramenta: N8N. 
Este repositório documentará os passos para criar um projeto para automação, ele realiza respostas de e-mail automáticas com API de inteligência artificial gratuita do Gemini.

<img width="1833" height="727" alt="fluxo-email-n8n" src="https://github.com/user-attachments/assets/10e04afc-7c35-4347-9400-0fae45db1041" />

## APIS NESCESSÁRIAS: 
- API cliente Google Cloud para conexão de contas google. (site: google cloud)
- API gemini (site: google AI studio)

## Permições: 
- Adicionar as permições na API Google Cloud: Google Drive, Google Sheets, Gmail, Google calendar

## Configuração da automação com suas contas google> 
- É nescessário ter em mãos o ID do cliente e a chave secreta para realizar login ao conectar o gmail no N8N.
- entre em GMAIL e selecione uma ação,
- Credential to connect with > create new credential:
- <img width="1920" height="877" alt="cadastrarcredencial" src="https://github.com/user-attachments/assets/ebed985e-d22a-4937-be55-2e85b1677b65" />

- <img width="1917" height="881" alt="logincomapi" src="https://github.com/user-attachments/assets/0612f26b-b948-42c3-8cda-ae2a46de8cbf" />

## VSP OU N8NCLOUD? 
- Para o desenvolvimento e teste do meu projeto, usei a VSP da Railway ( custo de $5 ao mês)
- Para o uso da N8NCLOUD o custo sera maior mas o desenvolvimento será mais facil..

## Lógica do projeto : 
- O programa verificará a cada minuto se existe uma nova mensagem na caixa de e-mail informada pela API do google cloud,
- <img width="1916" height="893" alt="image" src="https://github.com/user-attachments/assets/c670d5c2-a9b2-4cb6-af7b-d0e59b616098" />

- 
- (primeiro if:)caso a mensagem tenha sido enviada pelo meu outro e-mail ela não fará nada e o fluxo irá parar,
- <img width="1916" height="878" alt="if1" src="https://github.com/user-attachments/assets/d12ec8f8-9a41-43d2-bafc-b1f1e9f9b06e" />
- caso contrário: é feito uma transformação de dados para a IA compreender os campos:
- <img width="1915" height="878" alt="image" src="https://github.com/user-attachments/assets/2f16a046-25d8-4f33-94ff-e5586c3c379d" />
 a IA do Gemini lê o e-mail recebido e desenvolve uma resposta, que será enviada para aprovação humana,
- <img width="1907" height="868" alt="image" src="https://github.com/user-attachments/assets/3dd52f9c-976e-42f4-b08e-61959742918f" />

- é enviado o email da aprovação e ele aguarda sua resposta para concluir as proximas do fluxo,
- <img width="1917" height="874" alt="image" src="https://github.com/user-attachments/assets/a73ce752-66de-44ed-9e36-a7152804a734" />

- 
- (segundo if:)
- <img width="1920" height="874" alt="image" src="https://github.com/user-attachments/assets/930df4c7-6d4e-4f1b-9a75-8caed262c671" />

- caso a mensagem seja aprovada, a resposta é enviada ao rementente,
- <img width="1920" height="872" alt="image" src="https://github.com/user-attachments/assets/8589c692-b19e-4ee7-91f6-dc78bb52786a" />

- caso contrário, a IA reformula-rá uma nova resposta que passará novamente por aprovação. 
- <img width="1920" height="881" alt="image" src="https://github.com/user-attachments/assets/8478668f-ccb5-42ac-a245-f55ec3e2011a" />
- <img width="1920" height="871" alt="image" src="https://github.com/user-attachments/assets/751b0138-9478-4da5-a0fc-3b1a4205b2cd" />


