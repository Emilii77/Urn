# Urn
#OLiBel
from tkinter import*
#----------TELA 1-----------
class Funcao:
    def __init__(self):
        self.root= root
        self.tela()
        self.frame()
        self.botao()
        self.imagem()
        root.mainloop()
    
    def tela(self):
        self.root.title('URNA')
        self.root.geometry('740x800+740+60')
        self.root.resizable(False, False)
    
    def frame(self):
        self.frame1 = Frame(self.root, bg='#2d2d2d').place(relx=0.001, rely=0.001, relwidth=1, relheight=1)
        self.frame2 = Frame(self.frame1, bg='#fffff2').place(relx=0.05, rely=0.025, relwidth=0.9, relheight=0.95)
    
    def botao(self):
        
        self.avancar = Button (self.frame1,text='VOTAR ',font=('Arial', 15, 'bold'),bg = '#fffff2', command=self.comando1).place(relx=0.31, rely=0.86, relwidth=0.39, relheight=0.04)
        self.txt = Label(self.frame1, text= 'Canditados', font=('Lemon Milk', 30, 'bold'), bg='#fffff2').place(relx=0.36, rely=0.1)
    def imagem(self):
        self.imag = PhotoImage(file='xama.png')
        self.imag = self.imag.subsample(4, 4)
        self.image = Label(self.root, image = self.imag, bd = 0).place(relx = 0.08, rely = 0.35, relwidth =0.20, relheight =0.24)
        #texto
        self.txt2 = Label(self.frame1, text= 'Xamã', font=('Lemon Milk', 14, 'bold'), bg='#fffff2').place(relx=0.14, rely=0.60)
        self.txt = Label(self.frame1, text= '30', font=('Lemon Milk', 20, 'bold'), bg='#fffff2').place(relx=0.16, rely=0.64)
        
        self.imag1 = PhotoImage(file='azzy.png')
        self.imag1 = self.imag1.subsample(2, 2)
        self.image1 = Label(self.root, image = self.imag1, bd = 0).place(relx = 0.39, rely = 0.35, relwidth =0.20, relheight =0.24)
        #texto
        self.txt2 = Label(self.frame1, text= 'Azzy', font=('Lemon Milk', 14, 'bold'), bg='#fffff2').place(relx=0.45, rely=0.60)
        self.txt = Label(self.frame1, text= '24', font=('Lemon Milk', 20, 'bold'), bg='#fffff2').place(relx=0.46, rely=0.64)

        self.imag3 = PhotoImage(file='matue.png')
        self.imag3 = self.imag3.subsample(3, 3)
        self.image3= Label(self.root, image = self.imag3, bd = 0).place(relx = 0.70, rely = 0.35, relwidth =0.20, relheight =0.24)
        #texto
        self.txt2 = Label(self.frame1, text= 'Matuê', font=('Lemon Milk', 14, 'bold'), bg='#fffff2').place(relx=0.76, rely=0.60)
        self.txt = Label(self.frame1, text= '11', font=('Lemon Milk', 20, 'bold'), bg='#fffff2').place(relx=0.78, rely=0.64)

        #Colocar iamagem
    def comando1(self): # comando do botão
        self.hide()
        self.abrir= Tela2(self)

    def hide(self): # esconde a janela root
        self.root.withdraw()
    
    def show(self):
        self.root.update()
        self.root.deiconify() # mostra que volta a janela root
#---------------TELA 2------------------
class Tela2(Toplevel): #Tela Eça de Quiroz
    votos = []
    def __init__(self, receive): #inicialização
        self.rec=receive
        Toplevel.__init__(self)
        
    # Inserindo texto
        
     #Tela
        self.geometry('740x800+740+60') #tamanho da tela
        self.title('VOTAÇÃO') #titulo
        self.frame3 = Frame(self, bg='#2d2d2d').place(relx=0, rely=0, relwidth=1, relheight=1)
        self.frame4 = Frame(self, bg='#fffff2').place(relx=0.05, rely=0.025, relwidth=0.9, relheight=0.95)
    
        # Entrada de texto do voto
        self.entrar2 = Entry(self, bd =2)
        self.entrar2.bind("<Return>", self.mostrar_candidato)#Bind
        self.entrar2.place(relx = 0.1, rely = 0.4, height=30, width= 50)
        

        self.avanca2= Button(self, text='CONFIRMAR',font=('Arial', 15, 'bold'), fg= 'green',bg = '#fffff2', command=self.comando_fim)
        self.avanca2.place(relx=0.31, rely=0.86, relwidth=0.39, relheight=0.04)

        self.avanca3= Button(self, text='CANCELAR',font=('Arial', 15, 'bold'), fg= 'red' ,bg = '#fffff2', command=self.cancelar)
        self.avanca3.place(relx=0.1, rely=0.77, relwidth=0.3, relheight=0.04)

        self.avanca4= Button(self, text='BRANCO',font=('Arial', 15, 'bold'), fg= 'Black' ,bg = '#fffff2', command=self.comando_fim)
        self.avanca4.place(relx=0.60, rely=0.77, relwidth=0.3, relheight=0.04)

        self.avanca5 = Button (self, text= 'VERIFICAR CANDIDATO', font=('Arial', 15, 'bold'), fg= 'Black', bg = "white", command = self.mostrar_candidato)
        self.avanca5.place(relx=0.2, rely=0.4, relwidth=0.34, relheight=0.034)
        

    def candidato1(self):
        self.img = PhotoImage(file="xama.png")
        self.img = self.img.subsample(3, 3)
        self.lbl_img = Label(self, image=self.img)
        self.lbl_img.place(relx = 0.6, rely = 0.3, relwidth =0.3, relheight =0.31)

        self.txt1 = Label(self, text= 'Xamã', font=('Lemon Milk', 26, 'bold'), bg='#fffff2').place(relx=0.43, rely=0.48)
        self.txt2 = Label(self, text= '30', font=('Lemon Milk', 22, 'bold'), bg='#fffff2').place(relx=0.46, rely=0.53)

    def candidato2(self):
        self.img2 = PhotoImage(file="azzy.png")
        self.img2 = self.img2.subsample(2, 2)
        self.lbl_img2 = Label(self, image=self.img2)
        self.lbl_img2.place(relx = 0.6, rely = 0.3, relwidth =0.3, relheight =0.31)

        self.txt3 = Label(self, text= 'Azzy', font=('Lemon Milk', 30, 'bold'), bg='#fffff2').place(relx=0.43, rely=0.47)
        self.txt4 = Label(self, text= '24', font=('Lemon Milk', 25, 'bold'), bg='#fffff2').place(relx=0.46, rely=0.52)

    def candidato3(self):
        self.img3 = PhotoImage(file= 'matue.png')
        self.img3 = self.img3.subsample(2, 2)
        self.lbl_img3 = Label(self, image=self.img3)
        self.lbl_img3.place(relx = 0.6, rely = 0.3, relwidth =0.3, relheight =0.31)

        self.txt5 = Label(self, text= 'Matuê', font=('Lemon Milk', 24, 'bold'), bg='#fffff2').place(relx=0.43, rely=0.48)
        self.txt6 = Label(self, text= '11', font=('Lemon Milk', 22, 'bold'), bg='#fffff2').place(relx=0.46, rely=0.53)

    def mostrar_candidato(self, *args): # comando do botão
        self.votos.append(self.entrar2.get())
        print(self.entrar2.get())

        if self.entrar2.get() == '30':
            self.candidato1()
            self.entrar2.delete(0, END)
            

        elif self.entrar2.get() == '24': 
            self.candidato2()
            self.entrar2.delete(0, END)
            

        elif self.entrar2.get() =='11':
            self.candidato3()
            self.entrar2.delete(0, END)
            

        elif self.entrar2.get():
            self.txt5 = Label(self, text= 'CANDIDATO NÃO VALIDADO', font=('Lemon Milk', 14, 'bold'), fg= 'red', bg='#fffff2').place(relx=0.43, rely=0.58)
            

    def cancelar(self):
        self.hide()
        self.abrir= Tela2(self)

    def comando_fim(self):
        self.votos.append(self.entrar2.get())
        print(self.votos)
        self.hide()
        self.abrir= Tela3(self)

    def hide(self): # esconde a janela root
        self.withdraw()

    def show(self):
        self.update()
        self.deiconify()
#----------------TELA 3---------------
class Tela3(Toplevel): #Tela xama
    def __init__(self, receive):
        self.rec = receive
        Toplevel.__init__(self)
        self.geometry('740x800+740+60')
        self.title('FIM')

        self.frame3 = Frame(self, bg='#2d2d2d').place(relx=0.001, rely=0.001, relwidth=1, relheight=1)
        self.frame4 = Frame(self, bg='#fffff2').place(relx=0.05, rely=0.025, relwidth=0.9, relheight=0.95)

        self.titulo = Label(self, text='FIM', font=('Arial', 100, 'bold'), bg='#fffff2').place(relx=0.34, rely=0.34)
        self.conf = Button (self, text= 'FECHAR',font=('Arial', 34, 'bold'),bg = '#fffff2', command= exit).place(relx=0.08, rely=0.86, relwidth=0.84, relheight=0.09)

   
root = Tk()
Funcao()
