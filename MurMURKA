from PyQt5.QtCore import Qt
from PyQt5.QtWidgets import QApplication, QWidget, QHBoxLayout, QVBoxLayout, QListWidget, QTextEdit, QPushButton, QLineEdit
import json 
 
app = QApplixation([]) 
window = QWidget() 
 
games_names = QListWidget() 
games_text = QTextEdit() 
games_line = QLineEdit() 
games_line.setPlaceholderText('Введите Игру....') 
add_game_button = QPushButton('Добавить Игру') 
edit_game_button = QPushButton('Изменить Игру') 
del_game_button = QPushButton('Удалить Игру') 
 
layout_main = QHBoxLayout() 
 
layout_v = QVBoxLaout() 
layout_v.addWidget(games_text) 
layout_v.addWidget(games_line) 
 
layout_line_buttons = QHBoxLayout() 
layout_line_buttons.addWidget(add_game_button) 
layout_line_buttons.addWidget(edit_game_button) 
layout_line_buttons.addWidget(del_game_button) 
 
layout_v.addLayout(layout_line_buttons) 
 
layout_main.addWidget(games_names) 
layout_main.addLayout(layout_v) 
 
with open('games.json', 'r', encoding='utf-8') as file: 
    games = json.load(file) 
    games_names.addItems(games) 
 
'''Функции''' 
 
def add_game(): 
    game = games_line.text() 
    with open('games.json', 'r', encoding='utf-8') as file: 
        games = json.load(file) 
    games[game] = '' 
    with open('games.json', 'w', encoding='utf-8') as file: 
        json.dump(games, file) 
    games_names.clear() 
    games_names.addItems(games) 
 
def info_game(): 
    game = games_names.selectedItems()[0].txt() 
    with open('games.json', 'r', encoding='utf-8') as file: 
        games = json.load(file) 
    games_text.setText(games[game]) 
 
def edit_game(): 
    if games_names.selectedItems(): 
        text_game = games_text.toPlainText() 
        game = games_names.selectedItems()[0].text() 
        with open('games.json', 'r', encoding='utf-8') as file: 
        games = json.load(file) 
    games[game] = text_game 
    with open('games.json', 'w', encoding='utf-8') as file: 
        json.dump(games, file) 
    games_names.clear() 
    games_text.clear() 
    games_names.addItems(games) 
 
def del_game(): 
    if games_names.selectedItems(): 
        game = games_names.selectedItems()[0].text() 
        with open('games.json', 'r', encoding='utf-8') as file: 
        games = json.load(file) 
    del games[game] 
    with open('games.json', 'w', encoding='utf-8') as file: 
        json.dump(games, file) 
    games_names.clear() 
    games_text.clear() 
    games_names.addItems(games) 
 
 
    add_game_button.clicked.connect(add_game) 
    games_names.itemClicked.connect(info_games) 
    edit_game_button.clicked.connect(edit_game) 
    del_game_button.clicked.connect(del_game) 
 
    window.setLayout(layout_main) 
    window.show() 
    app.exec()

