# -*- coding: utf-8 -*-

__author__ = 'Leutskiy Evgeniy'

import pymorphy2

# Подключаем словари для морфологического анализа
morph = pymorphy2.MorphAnalyzer()

# Проверка на различные варианты значений граммем #

# Создаем собственный оператор switch-case для POS
def switch_case_pos(x):
    return {
        u'сущ' : u'имя существительное',
        u'гл' : u'глагол (личная форма)',
        u'прил' : u'имя прилагательное (полное)',
        u'кр_прил' : u'имя прилагательное (краткое)',
        u'комп' : u'компаратив',
        u'инф' : u'глагол (инфинитив)',
        u'прич' : u'причастие (полное)',
        u'кр_прич' : u'причастие (краткое)',
        u'деепр' : u'деепричастие',
        u'числительное' : u'числительное',
        u'н' : u'наречие',
        u'мс' : u'местоимение-существительное',
        u'предк' : u'предикатив',
        u'пр' : u'предлог',
        u'союз' : u'союз',
        u'част' : u'частица',
        u'межд' : u'междометие'
    }.get(x, u'------------ ')

# Создаем собственный оператор switch-case для Animacy
def switch_case_animacy(x):
    return {
        u'од' : u'одушевленное',
        u'неод' : u'неодушевленное'
    }.get(x, u'------------ ')

# Создаем собственный оператор switch-case для Aspect
def switch_case_aspect(x):
    return {
        u'сов' : u'совершенный вид',
        u'несрв' : u'несовершенный вид'
    }.get(x, u'------------ ')

# Создаем собственный оператор switch-case для Case
def switch_case_case(x):
    return {
        u'им' : u'именительный падеж',
        u'рд' : u'родительный падеж',
        u'дт' : u'дательный падеж',
        u'вн' : u'винительный падеж',
        u'тв' : u'творительный падеж',
        u'пр' : u'предложный падеж',
        u'зв' : u'звательный падеж',
        u'рд1' : u'первый родительный падеж',
        u'рд2' : u'второй родительный (частичный) падеж',
        u'вн2' : u'второй винительный падеж',
        u'пр1' : u'первый предложный падеж',
        u'пр2' : u'второй предложный (местный) падеж'
    }.get(x, u'------------ ')

# Создаем собственный оператор switch-case для Gender
def switch_case_gender(x):
    return {
        u'мр' : u'мужской род',
        u'жр' : u'женский род',
        u'ср' : u'средний род'
    }.get(x, u'------------ ')

# Создаем собственный оператор switch-case для Involvement
def switch_case_involvement(x):
    return {
        u'вкл' : u'говорящий включен',
        u'выкл' : u'говорящий не включен в действие'
    }.get(x, u'------------ ')

# Создаем собственный оператор switch-case для Mood
def switch_case_mood(x):
    return {
        u'изъяв' : u'изъявительное наклонение',
        u'повел' : u'повелительное наклонение'
    }.get(x, u'------------ ')

# Создаем собственный оператор switch-case для Number
def switch_case_number(x):
    return {
        u'ед' : u'единственное число',
        u'мн' : u'множественное число'
    }.get(x, u'------------ ')

# Создаем собственный оператор switch-case для Person
def switch_case_person(x):
    return {
        u'1л' : u'1 лицо',
        u'2л' : u'2 лицо',
        u'3л' : u'3 лицо'
    }.get(x, u'------------ ')

# Создаем собственный оператор switch-case для Tense
def switch_case_tense(x):
    return {
        u'наст' : u'настоящее время',
        u'прош' : u'прошедшее время',
        u'буд' : u'будущее время'
    }.get(x, u'------------ ')

# Создаем собственный оператор switch-case для Transitivity
def switch_case_transitivity(x):
    return {
        u'перех' : u'переходный',
        u'неперех' : u'непереходный'
    }.get(x, u'------------ ')

# Создаем собственный оператор switch-case для Voice
def switch_case_voice(x):
    return {
        u'действ' : u'действительный залог',
        u'страд' : u'страдательный залог'
    }.get(x, u'------------ ')

def get_all_characteristics(word):
    # Получаем разбор слова
    word_parse = morph.parse(word)[0]

    # Задаем значения равные количеству пробелов для отступов

    # на сколько увеличить смещение относительно стандартного
    delta = 1
    # стандартное смещение
    shift_from_border_left = 33
    # смещение оригинального слова
    name = shift_from_border_left + delta
    # смещение признака Одушевленность/Неодушевленность
    animacy = shift_from_border_left + delta
    # смещение признака Часть речи
    pos = shift_from_border_left + delta
    # смещение признака Вид глагола
    aspect = shift_from_border_left + delta
    # смещение признака Падеж
    case = shift_from_border_left + delta
    # смещение признака Пол
    gender = shift_from_border_left + delta
    # смещение признака Вовлеченность
    involvement = shift_from_border_left + delta
    # смещение признака Наклонение
    mood = shift_from_border_left + delta
    # смещение признака Число
    number = shift_from_border_left + delta
    # смещение признака Лицо
    person = shift_from_border_left + delta
    # смещение признака Время
    tense = shift_from_border_left + delta
    # смещение признака Переходность глагола
    transitivity = shift_from_border_left + delta
    # смещение признака Залог глагола
    voice = shift_from_border_left + delta

    #################################################################

    # Создаем список для результатов
    Result_Lines = []

    # Выводим исходное слово
    str_word_name = u'Исходное слово: '.ljust(name) + word_parse.word.upper()

    # Помещаем строку в список
    Result_Lines.append(str_word_name)

    # Часть речи (Part of Speech)
    str_pos_minus = u'Часть речи: '.ljust(pos) + switch_case_pos(unicode(word_parse.tag.POS))
    str_pos_plus = u'Часть речи: '.ljust(pos) + switch_case_pos(morph.lat2cyr(word_parse.tag.POS).lower()).upper()

    if unicode(word_parse.tag.POS) == u'None':
        Result_Lines.append(str_pos_minus)
    else:
        Result_Lines.append(str_pos_plus)

    # Одушевленность (Animacy)
    str_animacy_minus = u'Одушевленность/Неодушевленность: '.ljust(animacy) + switch_case_animacy(unicode(word_parse.tag.animacy))
    str_animacy_plus = u'Одушевленность/Неодушевленность: '.ljust(animacy) + switch_case_animacy(morph.lat2cyr(unicode(word_parse.tag.animacy)).lower()).upper()

    if unicode(word_parse.tag.animacy) == u'None':
        Result_Lines.append(str_animacy_minus)
    else:
        Result_Lines.append(str_animacy_plus)

    # Вид - совершенный или несовершенный (Aspect)
    str_aspect_minus = u'Вид глагола: '.ljust(aspect) + switch_case_aspect(unicode(word_parse.tag.aspect))
    str_aspect_plus = u'Вид глагола: '.ljust(aspect) + switch_case_aspect(morph.lat2cyr(unicode(word_parse.tag.aspect)).lower()).upper()

    if unicode(word_parse.tag.aspect) == u'None':
        Result_Lines.append(str_aspect_minus)
    else:
        Result_Lines.append(str_aspect_plus)

    # Падеж (Case)
    str_case_minus = u'Падеж: '.ljust(case) + switch_case_case(unicode(word_parse.tag.case))
    str_case_plus = u'Падеж: '.ljust(case) + switch_case_case(morph.lat2cyr(unicode(word_parse.tag.case)).lower()).upper()

    if unicode(word_parse.tag.case) == u'None':
        Result_Lines.append(str_case_minus)
    else:
        Result_Lines.append(str_case_plus)

    # Род (Gender)
    str_gender_minus = u'Род: '.ljust(gender) + switch_case_gender(unicode(word_parse.tag.gender))
    str_gender_plus = u'Род: '.ljust(gender) + switch_case_gender(morph.lat2cyr(unicode(word_parse.tag.gender)).lower()).upper()

    if unicode(word_parse.tag.gender) == u'None':
        Result_Lines.append(str_gender_minus)
    else:
        Result_Lines.append(str_gender_plus)

    # Включенность говорящего в действие (Involvement)
    str_involve_minus = u'Включенность: '.ljust(involvement) + switch_case_involvement(unicode(word_parse.tag.gender))
    str_involve_plus = u'Включенность: '.ljust(involvement) + switch_case_involvement(morph.lat2cyr(unicode(word_parse.tag.involvement)).lower()).upper()

    if unicode(word_parse.tag.involvement) == u'None':
        Result_Lines.append(str_involve_minus)
    else:
        Result_Lines.append(str_involve_plus)

    # Наклонение (повелительное, изъявительное) (Mood)
    str_mood_minus = u'Наклонение: '.ljust(mood) + switch_case_mood(unicode(word_parse.tag.mood))
    str_mood_plus = u'Наклонение: '.ljust(mood) + switch_case_mood(morph.lat2cyr(unicode(word_parse.tag.mood)).lower()).upper()

    if unicode(word_parse.tag.mood) == u'None':
        Result_Lines.append(str_mood_minus)
    else:
        Result_Lines.append(str_mood_plus)

    # Число (number)
    str_number_minus = u'Число: '.ljust(number) + switch_case_number(unicode(word_parse.tag.number))
    str_number_plus = u'Число: '.ljust(number) + switch_case_number(morph.lat2cyr(unicode(word_parse.tag.number)).lower()).upper()

    if unicode(word_parse.tag.number) == u'None':
        Result_Lines.append(str_number_minus)
    else:
        Result_Lines.append(str_number_plus)

    # Лицо - 1, 2, 3 (Person)
    str_person_minus = u'Лицо: '.ljust(person) + switch_case_person(unicode(word_parse.tag.person))
    str_person_plus = u'Лицо: '.ljust(person) + switch_case_person(morph.lat2cyr(unicode(word_parse.tag.person)).lower()).upper()

    if unicode(word_parse.tag.person) == u'None':
        Result_Lines.append(str_person_minus)
    else:
        Result_Lines.append(str_person_plus)

    # Время - настоящее, прошедшее, будущее (Tense)
    str_tense_minus =  u'Время: '.ljust(tense) + switch_case_tense(unicode(word_parse.tag.tense))
    str_tense_plus = u'Время: '.ljust(tense) + switch_case_tense(morph.lat2cyr(unicode(word_parse.tag.tense)).lower()).upper()

    if unicode(word_parse.tag.tense) == u'None':
        Result_Lines.append(str_tense_minus)
    else:
        Result_Lines.append(str_tense_plus)

    # Переходность - переходный, непереходный (transitivity)
    str_tran_minus = u'Переходность: '.ljust(transitivity) + switch_case_transitivity(unicode(word_parse.tag.transitivity))
    str_tran_plus = u'Переходность: '.ljust(transitivity) + switch_case_transitivity(morph.lat2cyr(unicode(word_parse.tag.transitivity)).lower()).upper()

    if unicode(word_parse.tag.transitivity) == u'None':
        Result_Lines.append(str_tran_minus)
    else:
        Result_Lines.append(str_tran_plus)

    # Залог - действительный, страдательный (voice)
    str_voice_minus = u'Залог: '.ljust(voice) + switch_case_voice(unicode(word_parse.tag.voice))
    str_voice_plus = u'Залог: '.ljust(voice) + switch_case_voice(morph.lat2cyr(unicode(word_parse.tag.voice)).lower()).upper()

    if unicode(word_parse.tag.voice) == u'None':
        Result_Lines.append(str_voice_minus)
    else:
        Result_Lines.append(str_voice_plus)

    return Result_Lines
