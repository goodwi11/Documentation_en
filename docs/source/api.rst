Подключение к API
=================

Главное про API
---------------

Для аутентификации в API используется HTTP-аутентификация типа Basic, где ключ API передается в качестве имени пользователя, а пароль оставляется пустым. То есть каждый запрос к API должен содержать обязательный заголовок Authorization вида:

``Authorization: Basic <authKey>``

Поле <authKey> в заголовке Authorization формируется путем base64-кодирования строки, составленной из ключа API и добавленного в конце двоеточия.

.. note::
    Вы можете найти ключ API в вашем профиле на сайте `Adspect <https://clients.adspect.ai/profile>`_.  

| Некоторые HTTP-клиенты имеют нативную поддержку аутентификации HTTP Basic и самостоятельно добавляют заголовок Authorization.
| Например, Python Requests предоставляет класс requests.auth.HTTPBasicAuth. В этом случае укажите ваш ключ API в качестве имени пользователя и оставьте пароль пустым.

.. | Для работы с API подается GET-запрос. Основной URL для использования API становится доступен после оформлении PRO-тарифа: https://api.comsign.io/v2?.
.. | Для авторизации API ключа в запрос добавляется следующий заголовок - headers: {'Authorization': 'Basic EnXSA1m3p3L0E0EHXVAzmWpzlkeyE1X6amm2P0LCEDg6’} 
.. | Заголовок Authorization можно найти в личном кабинете на сайте Adspect.

GET-параметры
-------------

Для генерации вайта (предпросмотра или ZIP-архива) нужно отправить HTTP GET-запрос на URL *https://api.comsign.io/v2*, указав настройки для генерации в URL-параметрах.

.. list-table::
   :header-rows: 1
   :stub-columns: 1

   * - Обязательно
     - Параметр
     - Для чего
   * - 
     - ``product``
     - выбор генератора:
       + sf – SafePage генератор. 
       + gp – GooglePlay генератор. 
       + ap – AppStore генератор. 
       + wp – Word Press (HTML) генератор.
       + wp&php=1 – Word Press (PHP) генератор.
   * - -
     - ``keywords``
     - ключевые слова для интеграции в вайт, прописывать через запятую.

.. - product - выбор генератора:
..  * sf – SafePage генератор. 
..  * gp – GooglePlay генератор. 
..  * ap – AppStore генератор. 
..  * wp – Word Press (HTML) генератор.
..  * wp&php=1 – Word Press (PHP) генератор.

.. - keywords – ключевые слова для интеграции в вайт, прописывать через запятую

.. - domain – доменное имя для интеграции в tos&privacy, прописывать в формате *https://example.com* или *example.com*

.. - lang – выбор необходимого языка для генерации. Прописывать в формате: язык_СТРАНА

.. - seed – номер генерации шаблона, случайный набор букв или цифр. Если значение параметра будет пустым, то seed сформируется автоматически

.. - target – тема или URL для наполнения вайта контентом. Для генераторов WP и SF необходимо прописать одну из доступных тем. Для генераторов Google Play и App Store используется URL-ссылка.

.. - zip=true – будет отдан ZIP-файл с вайтом. При активном параметре будет списываться лимит скаичваний. Если параметра «zip» нет, то вместо файла будет отдано превью. Если параметра «zip» нет, то вместо файла будет отдано JPG превью. 

.. - sid – параметр необходимый для интеграции потока с клоакой. Вытягивает фильтрационный файл filter.php и записывает index.php. Для активации параметра необходимо подставить ключ stream_id из потока Adspect.

Пример релевантной URL-ссылки для работы с API::

 https://api.comsign.io/v2?aid=2e2bbf52-adnc-5819-963c-8e0d48b26e9&keywords=example,example page&domain=example.com&lang=en_US&product=wp&sid=3eb2a9d3-9k93-3etc-ci88-ac1f6f92a854&target=food&zip=true

Коды доступных языков
---------------------

.. | Albanian - sq_AL  
.. | Amharic - am_ET  
.. | Arabian - ar_SA  
.. | Armenian - hy_AM  
.. | Azerbaijanian - az_AZ  
.. | Belarusian - be_BY  
.. | Bengal - bn_BD  
.. | Bulgarian - bg_BG  
.. | Burmese - my_MM  
.. | Chinese - zh_CH  
.. | Croatian - hr_HR  
.. | Czech - cs_CZ  
.. | Danish - da_DK  
.. | Dutch - nl_NL  
.. | English - en_US  
.. | Estonian - et_EE  
.. | Faroese - fo_FO  
.. | Finnish - fi_FI  
.. | French - fr_FR  
.. | Georgian - ka_GE  
.. | German - de_DE  
.. | Greek - el_GR  
.. | Guarani - gn_PY  
.. | Hebrew - he_IL 
.. | Hindi - hi_IN  
.. | Hungarian - hu_HU  
.. | Icelandic - is_IS  
.. | Indonesian - id_ID  
.. | Irish - ga_IE  
.. | Italian - it_IT  
.. | Japanese - ja_JP  
.. | Kazakh - kk_KZ  
.. | Khmer - km_KH  
.. | Korean - ko_KR  
.. | Kyrgyz - ky_KG  
.. | Lao - lo_LA  
.. | Latvian - lv_LV  
.. | Lithuanian - lt_LT  
.. | Luxembourgish - lb_LU  
.. | Macedonian - mk_MK  
.. | Malay - ms_MY  
.. | Maltese - mt_MT  
.. | Mongolian - mn_MN  
.. | Norwegian - no_NO  
.. | Persian - fa_IR  
.. | Polish - pl_PL  
.. | Portuguese - pt_PT  
.. | Punjabi - pa_IN  
.. | Romanian - ro_RO  
.. | Russian - ru_RU  
.. | Serbian - sr_RS  
.. | Slovenian - sl_SL  
.. | Spanish - es_ES  
.. | wahili - sw_KE  
.. | wati - ss_SZ  
.. | Swedish - sv_SE  
.. | Telugu - te_IN  
.. | Thai - th_TH  
.. | Turkish - tr_TR  
.. | Turkmen - tk_TM  
.. | Ukrainian - uk_UA  
.. | Urdu - ur_PK  
.. | Uzbek - uz_UZ  
.. | Vietnamese - vi_VN 
.. | Zulu - zu_ZA

===============   ======

Язык              Код

===============   ======
Албанский         sq_AL 
Амхарский         am_ET
Английский        en_US
Арабский          ar_SA
Армянский         hy_AM
Азербайджанский   az_AZ
Белорусский       be_BY
Бенгальский       bn_BD
Бирманский        my_MM
Болгарский        bg_BG
Венгерский        hu_HU
Вьетнамский       vi_VN
Голландский       nl_NL
Греческий         el_GR
Грузинский        ka_GE
Гуарани           gn_PY
Датский           da_DK
Зулу              zu_ZA
Иврит             he_IL
Исландский        is_IS
Испанский         es_ES
Итальянский       it_IT
Ирландский        ga_IE
Казахский         kk_KZ
Камбоджийский     km_KH
Китайский         zh_CH
Корейский         ko_KR
Кыргызский        ky_KG
Лаосский          lo_LA
Латышский         lv_LV
Литовский         lt_LT
Люксембургский    lb_LU
Македонский       mk_MK
Малайский         ms_MY
Мальтийский       mt_MT
Монгольский       mn_MN
Немецкий          de_DE
Норвежский        no_NO
Персидский        fa_IR
Польский          pl_PL
Португальский     pt_PT
Панджабский       pa_IN
Румынский         ro_RO
Русский           ru_RU
Сербский          sr_RS
Суахили           sw_KE
Свати             ss_SZ
Словенский        sl_SL
Тайский           th_TH
Телугу            te_IN
Турецкий          tr_TR
Туркменский       tk_TM
Украинский        uk_UA
Урду              ur_PK
Узбекский         uz_UZ
Финский           fi_FI
Французский       fr_FR
Хинди             hi_IN
Хорватский        hr_HR
Чешский           cs_CZ
Шведский          sv_SE
Эстонский         et_EE
Фарерский         fo_FO
Японский          ja_JP
===============   ======









