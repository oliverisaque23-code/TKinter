
import tkinter as tk

# Criar a janela principal
janela = tk.Tk()

# Definir o título da janela
janela.title("Minha Primeira Janela")

# Definir o tamanho da janela (largura x altura)
janela.geometry("400x300")

# Iniciar o loop da aplicação (exibe a janela)
janela.mainloop()




import tkinter as tk

def clicar_botao():
    rotulo.config(text="Botão clicado!")

janela = tk.Tk()
janela.title("Exemplo de Botão e Rótulo")
janela.geometry("300x150")

rotulo = tk.Label(janela, text="Clique no botão.")
rotulo.pack(pady=10) 

botao = tk.Button(janela, text="Clique aqui", command=clicar_botao)
botao.pack()

janela.mainloop()



import tkinter as tk

janela = tk.Tk()
janela.title("Meu App Colorido")
janela.geometry("500x300")
janela.configure(bg="yellow")  

janela.mainloop()




import tkinter as tk

def dizer_ola():
    nome = entrada_nome.get()
    rotulo_resultado.config(text=f"Olá, {nome}.")

janela = tk.Tk()
janela.title("Cumprimento com Nome")
janela.geometry("300x150")

entrada_nome = tk.Entry(janela, width=30)
entrada_nome.pack(pady=10)

botao_enviar = tk.Button(janela, text="Enviar", command=dizer_ola)
botao_enviar.pack()

rotulo_resultado = tk.Label(janela, text="")
rotulo_resultado.pack(pady=10)

janela.mainloop()




import tkinter as tk

contador = 0

def contar_clique():
    global contador
    contador += 1
    rotulo.config(text=f"Botão clicado {contador} vezes")

janela = tk.Tk()
janela.title("Contador de Cliques")
janela.geometry("300x150")

rotulo = tk.Label(janela, text="Botão clicado 0 vezes")
rotulo.pack(pady=10)

botao = tk.Button(janela, text="Clique aqui", command=contar_clique)
botao.pack()



import tkinter as tk

def muda_cor_vermelha():
    janela.configure(bg="red")

def muda_cor_verde():
    janela.configure(bg="green")

def muda_cor_azul():
    janela.configure(bg="blue")

janela = tk.Tk()
janela.title("Janela Colorida")
janela.geometry("400x300")

btn_vermelho = tk.Button(janela, text="Vermelho", command=muda_cor_vermelha, width=10)
btn_vermelho.pack(pady=10)

btn_verde = tk.Button(janela, text="Verde", command=muda_cor_verde, width=10)
btn_verde.pack(pady=10)

btn_azul = tk.Button(janela, text="Azul", command=muda_cor_azul, width=10)
btn_azul.pack(pady=10)

janela.mainloop()

janela.mainloop()



import tkinter as tk
from tkinter import messagebox

def verificar_login():
    usuario = entrada_usuario.get()
    senha = entrada_senha.get()
    
    if usuario == "admin" and senha == "123":
        messagebox.showinfo("Login", "Acesso permitido")
    else:
        messagebox.showerror("Login", "Acesso negado")

janela = tk.Tk()
janela.title("Tela de Login")
janela.geometry("300x180")

tk.Label(janela, text="Usuário:").pack(pady=5)
entrada_usuario = tk.Entry(janela)
entrada_usuario.pack()

tk.Label(janela, text="Senha:").pack(pady=5)
entrada_senha = tk.Entry(janela, show="*") 
entrada_senha.pack()

btn_login = tk.Button(janela, text="Entrar", command=verificar_login)
btn_login.pack(pady=15)

janela.mainloop()



import tkinter as tk
from tkinter import messagebox

def verificar_login():
    usuario = entrada_usuario.get()
    senha = entrada_senha.get()

    if usuario == "admin" and senha == "123":
        messagebox.showinfo("Login", "Acesso permitido")
    else:
        messagebox.showerror("Login", "Acesso negado")


janela = tk.Tk()
janela.title("Tela de Login")
janela.geometry("300x180")
janela.resizable(False, False) 

tk.Label(janela, text="Usuário:").pack(pady=(20,5))
entrada_usuario = tk.Entry(janela)
entrada_usuario.pack()

# Label e Entry para senha
tk.Label(janela, text="Senha:").pack(pady=5)
entrada_senha = tk.Entry(janela, show="*")
entrada_senha.pack()

btn_login = tk.Button(janela, text="Entrar", command=verificar_login)
btn_login.pack(pady=15)

janela.mainloop()




import tkinter as tk

def atualizar_mensagem(mensagem):
    rotulo.config(text=mensagem)
    
janela = tk.Tk()
janela.title("Saudações")
janela.geometry("300x150")

rotulo = tk.Label(janela, text="", font=("Arial", 14))
rotulo.pack(pady=10)

btn_bom_dia = tk.Button(janela, text="Bom dia", command=lambda: atualizar_mensagem("Bom dia!"))
btn_bom_dia.pack(side="left", expand=True, padx=10)

btn_boa_tarde = tk.Button(janela, text="Boa tarde", command=lambda: atualizar_mensagem("Boa tarde!"))
btn_boa_tarde.pack(side="left", expand=True, padx=10)

btn_boa_noite = tk.Button(janela, text="Boa noite", command=lambda: atualizar_mensagem("Boa noite!"))
btn_boa_noite.pack(side="left", expand=True, padx=10)


janela.mainloop()





import tkinter as tk

def contador_regressivo(contador):
    if contador >= 0:
        rotulo.config(text=str(contador))
      
        janela.after(1000, contador_regressivo, contador - 1)
    else:
        rotulo.config(text="Fim!")

# Criar janela principal
janela = tk.Tk()
janela.title("Contador Regressivo")
janela.geometry("200x100")


rotulo = tk.Label(janela, text="", font=("Arial", 40))
rotulo.pack(expand=True)


contador_regressivo(10)


janela.mainloop()




import tkinter as tk

janela = tk.Tk()
janela.title("Rótulo Personalizado")
janela.geometry("300x100")


rotulo = tk.Label(janela, text="Texto Personalizado", font=("Arial", 20), fg="blue")
rotulo.pack(pady=20)

janela.mainloop()




import tkinter as tk
from tkinter import messagebox

def salvar_compromisso():
    compromisso = entrada_compromisso.get()
    if compromisso.strip() == "":
        messagebox.showwarning("Aviso", "Digite um compromisso antes de salvar.")
        return
    lista_compromissos.insert(tk.END, compromisso)
    entrada_compromisso.delete(0, tk.END)

def sair_aplicacao():
    janela.destroy()

janela = tk.Tk()
janela.title("Compromissos")
janela.geometry("400x300")

tk.Label(janela, text="Digite o compromisso:").pack(pady=5)
entrada_compromisso = tk.Entry(janela, width=50)
entrada_compromisso.pack(pady=5)

btn_salvar = tk.Button(janela, text="Salvar", command=salvar_compromisso)
btn_salvar.pack(pady=5)

lista_compromissos = tk.Listbox(janela, width=50, height=10)
lista_compromissos.pack(pady=10)

btn_sair = tk.Button(janela, text="Sair", command=sair_aplicacao)
btn_sair.pack(pady=5)

janela.mainloop()



import tkinter as tk

def sair():
    janela.destroy()

janela = tk.Tk()
janela.title("Janela com Botão Sair")
janela.geometry("200x100")

btn_sair = tk.Button(janela, text="Sair", command=sair)
btn_sair.pack(expand=True)

janela.mainloop()


