# -*- coding: utf-8 -*-

# автор скрипта
__author__ = 'Leutskiy Evgeniy'

# подключаем библиотеку pymorphy2
import pymorphy2
# подключаем токенизатор из pymorphy2
import pymorphy2.tokenizers
# подключаем модуль с основными функциями
import MainFunctions

# строим токенизатор
tokenization = pymorphy2.tokenizers
# строим морфологический анализатор
morph = pymorphy2.MorphAnalyzer()

# считываем фразы из файла
try:
    f_read = open("queries.txt", "r")
except IOError:
    print 'Not file'

 # Запишем результаты в файл:

# Открываем файл
try:
    f = open("result_pymorphy2.txt","w")
except IOError:
    print 'Not file'

# составляем список поисковых фраз
for query in list(f_read):
    # помещаем в файл заголовок
    f.write((u'------------------------------------------------------' + u'\n').encode('utf-8'))
    f.write(query.decode('cp1251').encode('utf-8'))
    f.write((u'------------------------------------------------------' + u'\n').encode('utf-8') )
    # получаем запрос в нужной кодировке unicode
    s = query.decode('cp1251')

    # разбиваем запрос на токены
    tokens_in_query = tokenization.simple_word_tokenize(s)

    # счетчик
    count = 0

    # для каждого токена получаем набор характеристик
    for token in tokens_in_query:
        # увеличивем счетчик
        count = count + 1
        # получаем корректный набор характеристик для токена
        list = MainFunctions.get_all_characteristics(token)

        # выводим данные на консоль
        for line in list:
            # Записываем стороки разбора в нужном формате и кодировке в файл
            f.write((line + u'\n').encode('utf-8') )

        print count , len(tokens_in_query)

        if count != len(tokens_in_query):
            f.write((u'--------------------------------' + u'\n').encode('utf-8') )

# Закрываем файлы
f_read.close()
f.close()

##########################################################################
