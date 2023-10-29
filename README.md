# pyqt5: Primerios_Passos
Possui um passo a passo pra aprender a usar o Pyqt5
<h1>Passo 1: Instalar os módulos</h1>

```bash
pip install pyqt5
pip install pyqt5-tools
```
<h1>Passo 2: Criar uma Janela</h1>

```bash
#importando os modulos necessários
from PyQt5 import QtWidgets
from PyQt5.QtWidgets import QApplication, QMainWindow, QLabel
import sys

def main():
   
    app = QApplication(sys.argv)  #configura o aplicativo
    
    win = QMainWindow() #cria uma janela
    win.setGeometry(200,200,300,300) # seta as dimensões da janela
    win.setWindowTitle("My first window!") #seta o nome da janela

    #exibe o texto na janela
    label = QLabel(win)
    label.setText("my first label")
    label.move(50, 50)  
    win.show() # exibe a janela

    sys.exit(app.exec_()) #fecha a janela com sucesso

main()  # chama o codigo
```
<h1>Passo 3: adicionando botões</h1>
<p>1. Para adicionar botões basta seguir o padrão</p>

```bash
b1 = QtWidgets.QPushButton(win)
b1.setText("click me")
b1.move(100,100) 
```
<p>2. Você pode criar funções e chamá-las por meio dos botões</p>

```bash
from PyQt5 import QtWidgets
from PyQt5.QtWidgets import QApplication, QMainWindow, QLabel
import sys


def clicked():
    print("clicked") 

def main():
    app = QApplication(sys.argv)
    win = QMainWindow()
    win.setGeometry(200,200,300,300) 
    win.setWindowTitle("My first window!") 
    
    label = QLabel(win)
    label.setText("my first label")
    label.move(50, 50)  

    b1 = QtWidgets.QPushButton(win)
    b1.setText("click me")
    b1.move(100,100) 

    b1.clicked.connect(clicked) #aqui é atribuida a função clicked ao botão b1

    win.show()
    sys.exit(app.exec_())

main()
```
<h1>Passo 4: Trabalhando com classe</h1>

```bash
from PyQt5 import QtWidgets
from PyQt5.QtWidgets import QApplication, QMainWindow
import sys


class MyWindow(QMainWindow):
    #configura a janela
    def __init__(self):
        super(MyWindow,self).__init__()
        self.initUI()

    def button_clicked(self):
        self.label.setText("you pressed the button")
        self.update()

    #configura  que aparece na janela
    def initUI(self):
        self.setGeometry(200, 200, 300, 300)
        self.setWindowTitle("Tech With Tim")

        self.label = QtWidgets.QLabel(self)
        self.label.setText("my first label!")
        self.label.move(50,50)

        self.b1 = QtWidgets.QPushButton(self)
        self.b1.setText("click me!")
        self.b1.clicked.connect(self.button_clicked)

    def update(self):
        self.label.adjustSize()

# a funcao main
def window():
    app = QApplication(sys.argv)
    win = MyWindow()
    win.show()
    sys.exit(app.exec_())

window()
```
<h1>Passo 5: Usando o QT design</h1>
<p>1. Vá em seus arquivos e procure por AppData, de lá busque na pasta Python o executável do Qt design</p>
<p>2. Gere uma interface e saLve o arquivo .ui na pasta onde esta desenvolvendo</p>
<p>3. Com o  prompt de comando digite:</p>

```bash
pyuic5 -x teste.ui -o arquivo.py
```
