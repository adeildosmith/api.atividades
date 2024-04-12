# api.atividades
Esse será um api com SQLAlchemy

from models import Pessoas, Usuarios

#Insere dados na tabela pessoa
def insere_pessoas():
    pessoa = Pessoas(nome='Adeildo',idade=49)
    print(pessoa)
    pessoa.save()

#Realize consulta na tabela pessoa
def consulta_pessoas():
    pessoa = Pessoas.query.all()
    print(pessoa)
    pessoa = Pessoas.query.filter_by(nome='Felipe').first()
    print(pessoa.idade)

#Altera dados na tabela pessoa
def altera_pessoa():
    pessoa = Pessoas.query.filter_by(nome='Galeano').first()
    pessoa.idade = 21
    pessoa.save()
#Exclui dados na tabela pessoa
def exclui_pessoa():
    pessoa = Pessoas.query.filter_by(nome='Rafael').first()
    pessoa.delete()

def insere_usuarios(login, senha):
    usuario = Usuarios(login=login, senha=senha)
    usuario.save()

def consulta_todos_usuarios():
    usuarios = Usuarios.query.all()
    print(usuarios)

if __name__ == ' __main__':
    insere_usuarios('adeildo', 'rafael', '1234')
    insere_usuarios('galeano', '4321')
    consulta_todos_usuarios()
    #altera_pessoa()
    #exclui_pessoa()
    #consulta_pessoas()
    #insere_pessoas()





