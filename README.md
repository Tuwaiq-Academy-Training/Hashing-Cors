
- ماهي Hashing ؟
- ماهي SQL injection
-  ماهي XSS (cross site scripting)
- ماهي تزوير الطلب عبر المواقع (Cross Site Request Forgery)


##  ماهي  hashing؟

ال hashing هي عملية تحويل مفتاح معين إلى قيمة أخرى. تُستخدم دالة التجزئة لتوليد القيمة الجديدة وفقًا لخوارزمية رياضية. تُعرف نتيجة دالة التجزئة باسم قيمة التجزئة أو ببساطة التجزئة.

![hash](https://user-images.githubusercontent.com/92247967/201050028-dd6db11c-cb37-4aad-9d78-c28d448654a3.png)


تستخدم دالة hash الجيدة خوارزمية hash أحادية الاتجاه ، أو بمعنى آخر ، لا يمكن تحويل hash مرة أخرى إلى المفتاح الأصلي.

![one-way](https://user-images.githubusercontent.com/92247967/201051294-7f8cb869-40b4-4ff0-98b7-c9055f636b41.png)


## الاصطدامات

ضع في اعتبارك أن مفتاحين يمكن أن يولدا نفس hash. تُعرف هذه الظاهرة بالاصطدام. هناك عدة طرق للتعامل مع الاصطدامات ، ولكن هذا موضوع لوقت آخر.

![Collisions](https://user-images.githubusercontent.com/92247967/201052348-8a6872f5-d167-481a-801f-e554d013e6d2.png)


## ماهي SQL injection

ال sql injection  من بين أكثر الثغرات تواجدا على مواقع الأنترنيت و هو ببساطة هجوم يتم فيه حقن كود sql بتطبيق الويب حتى يتم استخراج البيانات من قاعدة االبيانات التي يعتمد عليها الموقع ، والثغرة تعتمد على خطأ في عدم معاينة ما يتم إدخاله قبل ان يتم تمريره لقاعدة البيانات ،كما يمكنك تجاوز نافذة authentication باستعمال هذه الثغرة،  و بالنسبة لتدونتنا سنقوم فقط بشرح استخراج البيانات باعتماد Union .


#### وهذه صورة توضح استغلال ثغرة sql injection 


![image](https://3.bp.blogspot.com/-8qz37_nGlHA/WEVz_hGP9sI/AAAAAAAAAfg/kbihxRSPa-QoCquvsb-3y4Gb96y-zpaLACEw/s1600/sql-injection.png)


## ماهي ماهي XSS (cross site scripting)

تعد XSS من أشهر الهجمات على الويب والتي تتم عبر حقن موقعك بسكريبت يقوم بتنفيذ أوامر خبيثة على حواسيب الزوار، أي أن موقعك يتحول إلى وسيلة لاصطياد الضحايا عبر سكريبت يزرعه المخترق في موقعك.
في XSS لا يستهدف المخترق موقعك بدرجة أولى، وإنما يستعمله كجسر للعبور إلى الضحايا الذين يتصفحونه، حيث يستغل ثغرة في موقعك يتسلل من خلالها إلى زوار موقعك للهجوم عليهم.
و XSS هي اختصار ل Cross Site Scripting، هل لاحظت شيئا؟
نقول XSS بينما الاختصار ينبغي أن يكون CSS، فلماذا يا ترى؟
حتى لا نخلط بين مسمى الثغرة وبين لغة الأنماط CSS المعروفة، لذلك تم استبدال حرف C ب X دلالة على Cross والتي تعني بالانجليزية شارة التقاطع وهي ترسم على هيئة X، لذلك تسمى Cross Site Scripting اختصارا ب XSS.
نعود ونعرف باختصار، ثغرة XSS هي ثغرة تسمح للمخترق بزرع أو حقن سكريبت بأي لغة يدعمها المتصفح الذي يستعمله زائر موقعك، وغالبا ما يكون هذا السكريبت بلغة جافاسكريبت، وعند تصفح الموقع يتم تنفيذ هذا السكريبت مما يهدد الزائر.

## كيف تعمل XSS؟

أولا في هجوم XSS عندنا ثلاث فاعلين وهم كالتالي:
- الضحية وهو زائر موقعك
- الوسيلة أو الجسر وهو موقعك نفسه
- ثم المخترق وهو الذي يستغل موقعك للإيقاع بالزوار
وفي هجوم XSS يقوم المخترق باستغلال إحدى طرق إدخال البيانات إلى الموقع، وليكن مثلا عبر حقول إدخال النص Input Text Fields، فيرسل بيانات على شكل سكريبت، بعد ذلك يتم تنفيذ هذا السكريبت على متصفح الزائر، وتختلف هجمات XSS باختلاف طريقة التعامل مع السكريبت المحقون، إما أن يخزن في قاعدة بيانات ثم ينفذ عند استدعائه، وإما أن ينفذ مباشرة دون أن يحفظ عبر دمجه في رابط معين.
طبعا الكلام مايزال مبهما بعض الشيء، لكن بالمثال يتضح المقال.


## ماهي أنواع XSS؟
توجد ثلاثة أنواع من هجمات XSS كلها قائمة على نفس المبدأ المتمثل في استغلال موقع عبر إرسال سكريبت يتم تنفيذه على مستوى متصفح الزائر.
وهذه الأنواع الثلاثة من أنواع XSS كما يلي:

- ال Stored XSS : وتسمى كذلك Persistent XSS: وتحدث هذه الثغرة حينما يقوم المخترق باستغلال أحد مدخلات الموقع فيقوم بإرسال سكريبت يتم تخزينه على مستوى سيرفر الموقع وغالبا في قاعدة البيانات Database، كأن يرسل السكريبت من مربع كتابة التعليقات في الموقع، أو على شكل رسالة، أو من أي مكان في الموقع يسمح بتخزين القيم في قاعدة البيانات، وحينما يأتي زائر ليستعرض الصفحة التي تحتوي على القيم القادمة من قاعدة البيانات يتم تنفيذ هذا السكريبت. على سبيل المثال قمت ببرمجة مدونة Blog من أجل نشر المقالات عليها، في إحدى مقالاتك دخل المخترق وبدل أن يكتب لك تعليقا قام بكتابة سكريبت، هذا السكريبت سيتم تخزينه في قاعدة البيانات، وبالتالي حينما سيأتي زائر ما ليستعرض مقالتك سيتم تحميل التعليقات من قاعدة البيانات ومعها التعليق الملغوم.

- ال Reflected XSS : وتسمى كذلك Non-persistent XSS، وتحدث حينما يستغل المخترق إحدى مدخلات الموقع دون الحاجة إلى تخزين السكريبت في قاعدة البيانات، فيقوم بإرسال رابط الموقع مدموجا بسكريبت ملغوم إلى الضحية عبر إيميل مثلا، أو من خلال نشر هذا الرابط على موقع ما أو على مواقع السوشيال ميديا، وحينما يضغط الضحية على الرابط سيذهب به إلى الموقع وستم تنفيذ السكريبت المدمج معه وبالتالي سيحصل المخترق على ما يشاء، إما عبر سرقة Cookies أو من خلال KeyLogging أو القيام بعمليات أخرى.

- ال Dom-based XSS : وهو شبيه جدا بالنوع Reflected XSS، غير أنه يرتكز بالأساس على التحكم في Dom الخاص بالصفحة عبر تنفيذ سكريبت مكان إرسال قيمة معينة.


## كيف تستطيع جافا سكريبت التأثير على بيانات الزائر؟

تنفيذ جافاسكريبت على متصفح الزائر لا يشكل أي خطر على الإطلاق ماعدا ما سنذكره لاحقا، لأن جافاسكريبت تشتغل في بيئة محدودة الصلاحيات تمنعها من الوصول إلى ملفات المستخدم وإلى نظام التشغيل، ويمكنك تجربة ذلك بنفسك، من خلال فتح مفكرة نوتباد ومحاولة  حذف ملف أو إعادة تسميته من خلال أوامر جافاسكريبت ستجد أن ذلك غير ممكن باستخدام جافاسكريبت لوحدها.
لكن تأتي خطورة جافاسكريبت من قدرتها على الوصول إلى بعض بيانات المستخدم الحساسة ك Cookies، ومن قدرتها على إرسال HTTP Requests لمحتوى معين إلى وجهة معينة من خلال أجاكس أي تستطيع إرسال البيانات إلى السرفر، وكذلك من قدرتها على تعديل HTML  الخاص بالصفحة التي ينفذ عليها سكريبت بسبب DOM methods.
هنا تتجلى الخطورة في تنفيذ أوامر جافاسكريبت على متصفح الزائر، بحيث يكفي تنفيذ أمر document.cookie للحصول على Cookie المرتبط بالموقع ومن ثم إرساله إلى السرفر الخاص بالمخترق من أجل العثور على بعض المعلومات الحساسة مثل معرف Session ID.
أو من خلال تسجيل الحروف Keylogging بحيث يتم قنص الحدث الخاص بالضغط على أزرار لوحة المفاتيح وتسجيل كل ما يتم كتابته وإرساله بعد ذلك إلى سرفر المخترق وقد تشمل النصوص المكتوبة كلمات السر وأرقام بطاقة الائتمان وغيرها..
كما يمكن للمخترق أن يغير DOM الخاص بالصفحة من خلال إضافة فورم إلى الموقع ويضع في action attribute  وجهة الإرسال وبالتالي يمكنه استغلال هذا الأمر في عملية Phishing عبر دفع المستخدم إلى إدخال بعض المعلومات الحساسة وهو يظن أنه يدخلها في الموقع وفي الحقيقة سيتم إرسالها إلى سيرفر المخترق.

## ماهي تزوير الطلب عبر المواقع (cross site request forgery)

هجمات التطبيقات آخذة في الارتفاع وأصبحت أكثر تقدمًا. في المتوسط ​​، تحتوي التطبيقات على أكثر من 10 نقاط ضعف عند إطلاقها في الإنتاج ، مما يترك فرصًا كبيرة للمهاجمين لاستغلالها. نظرًا لأنه يتم دفع المطورين إلى تسريع دورات الإصدار للتطبيقات المحسنة والمعقدة ، يجب عليهم تحديد أولويات معالجة الثغرات الأمنية بسرعة وفعالية. في كثير من الأحيان ، يتم إهمال الثغرات الأمنية الخاصة بالتزوير عبر المواقع (CSRF) ولا يتم إصلاحها قبل إصدار التعليمات البرمجية في الإنتاج.

ما ورد أعلاه صحيح لأن هجمات تطبيق CSRF لا تؤدي إلا إلى تغييرات الحالة عندما تنجح ، مما يعني أن بيانات المستخدم ليست في خطر. على الرغم من عدم تعرض البيانات الشخصية للمستخدم لأذى ، فإن معلومات التعريف الشخصية (PII) وكلمات المرور وحتى الأموال معرضة للخطر. يركز المطورون وفرق أمان التطبيقات على الهجمات الأكثر تقدمًا التي قد تؤدي إلى كشف حساس للبيانات ؛ نتيجة لذلك ، لا يتم معالجة نقاط الضعف CSRF ، مما يترك لمجرمي الإنترنت مع المزيد من الفرص للتنفيذ الناجح.


## ما هو CSRF؟
تتلاعب هجمات تطبيق CSRF بتطبيق الويب الخاص بالمستخدم لتنفيذ أوامر غير مرغوب فيها. يستفيد هجوم CSRF من حقيقة أن التطبيقات لا تملك القدرة على التعرف على الفرق بين الطلبات الضارة والآمنة بمجرد مصادقة المستخدم. عادةً ما يبدأ المهاجمون العملية عن طريق إنشاء رابط تالف يرسلونه إلى الهدف عبر البريد الإلكتروني أو الرسائل النصية أو الدردشة. غالبًا ما يُشار إلى هجوم CSRF على أنه هجوم "أحادي الاتجاه" ، حيث يمكن للمهاجمين الوصول إلى طلبات HTTP ومعالجتها ولكن لا يمكنهم الوصول إلى الاستجابات التالية. لذلك ، فهم يستهدفون طلبات تغيير الحالة داخل التطبيق ، ويتركون البيانات الحساسة بشكل عام دون أن يلحق بهم أذى.

من ناحية أخرى ، فإن هجوم البرمجة النصية عبر المواقع (XSS) هو هجوم "ثنائي الاتجاه" ، مما يسمح للممثلين السيئين ليس فقط بالتلاعب بالطلبات ولكن أيضًا قراءة الردود وحتى استخراج البيانات. في هجمات XSS ، يتدخل مجرمو الإنترنت في برنامج نصي من جانب المتصفح ، ويحقنونه في مواقع الويب الموثوقة. لا تقتصر هجمات XSS على الإجراءات التي يمكن للمستخدمين فقط تنفيذها ، وبالتالي يمكنهم تعريض المحتوى والكود على صفحة HTML بأكملها للخطر. يتمثل الاختلاف الأكثر بروزًا بين الاثنين في المصادقة ، حيث تتطلب هجمات CSRF تسجيل دخول ناجح للمستخدم ، في حين أن هجمات XSS لا تتطلب ذلك.

## كيف يعمل هجوم تطبيق CSRF؟

تعمل هجمات CSRF من خلال استهداف نقاط الضعف في تطبيقات الويب ، مما يجعلها غير قادرة على التمييز بين الأوامر الصالحة والخبيثة. تم تصميم تطبيقات الويب لتضمين ملفات تعريف الارتباط وملفات تعريف الارتباط للجلسة تلقائيًا بمجرد نجاح المصادقة. ينشئ المهاجمون أولاً عنوان URL يحاكي الإجراء الذي يرغبون في تنفيذه بمجرد مصادقة المستخدم. بعد ذلك ، يجب أن يبتكروا وسيلة توصيل ذكية أو رابطًا يحتوي على أعلى احتمالية أن ينقر عليه المستخدم. للتنفيذ الناجح ، يجب تسجيل الهدف في تطبيق وفي جلسة نشطة. بمجرد مصادقة المستخدم والنقر فوق الارتباط الضار ، يكون لدى المهاجمين كل ما يحتاجون إليه لمعالجة الطلبات. يتضمن ذلك تغيير البريد الإلكتروني للهدف ، والسماح بالتحويلات غير المرغوب فيها من الحسابات المصرفية ، أو إجراء عمليات شراء غير مرغوب فيها.

نظرًا لأن ملفات تعريف الارتباط تحتوي على بيانات المصادقة ، فإنها تسمح بتسجيل دخول أسرع وجلسات ممتدة. في حين أن هذا مناسب للمستخدمين ، يمكن للمهاجمين استغلال الثغرة الأمنية في هذا التطبيق من خلال الاستمرار في المصادقة في حساب المستخدم طالما سمحت الجلسة بذلك. أثناء جلسة المصادقة ، يتمتع المهاجمون بحق الوصول الكامل إلى حساب المستخدم ويمكنهم إجراء أي عدد من التغييرات دون تشغيل تنبيه.
