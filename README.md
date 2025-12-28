🧠 Projeto ETL — Santander Dev Week
Este projeto demonstra um fluxo completo de ETL (Extract, Transform, Load) utilizando Python e Pandas.
O objetivo é simular um cenário real de processamento de dados, gerando mensagens personalizadas para usuários a partir de um arquivo CSV.

📥 1. Extract — Extração
Os dados são lidos a partir do arquivo usuarios.csv, contendo:

id

nome

conta

cartao
df = pd.read_csv("usuarios.csv")

🔄 2. Transform — Transformação
Uma função gera mensagens personalizadas para cada usuário:
def gerar_mensagem(nome, conta, cartao):
    return f"Olá {nome}, sua conta {conta} está ativa e seu cartão {cartao} já está disponível."

df["mensagem"] = df.apply(
    lambda row: gerar_mensagem(row["nome"], row["conta"], row["cartao"]),
    axis=1
)

📤 3. Load — Carregamento
O resultado é salvo em um novo arquivo:
df.to_csv("usuarios_com_mensagens.csv", index=False)

📁 Arquivos incluídos
usuarios.csv — dados originais

usuarios_com_mensagens.csv — dados transformados

etl.ipynb 



