# Python Ecommerce

#### Projeto aprensentado por Gabriel Casimiro, evento workshop rocketseat de 15 à 17 de Janeiro-24

#### 1º acesso:
Após config do banco de dados:
app.config['SQLALCHEMY_DATABASE_URI'] = 'sqlite:///ecommerce.db'

E criação do Model da Tabela Product

no terminal digitar flask shell:
* db.create_all()
* db.session.commit()
* exit()

Iniciar o servidor:
* flask --app app run

CORS:
* Usado para permitir acessos de sistemas externos

UserMixin:
* Já possui metodos de ativo, inativo, authenticate ....

Criação de Usuario:
---
Reprocessar o banco recriando as tabelas
* db.drop_all()
* db.create_all()
* db.session.commit()
* exit()

login_user:
* para autenticar o usuario

Login_manager:
* usado para gerenciamento da authenticação, sobre a rota de login
* necessario criação de secret_key:
        app.config['SECRET_KEY']

login_required:
* Obriga o usuario estar authenticado
* necessário a criação de uma função de user_loader:
```python
@login_manager.user_loader
def load_user(user_id):
    return User.query.get(int(user_id))
```
---

Feito com ❤ por Rafael D. Silva