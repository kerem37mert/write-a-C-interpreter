Bu yazı serisinde sıfırdan bir C derleyicisi oluşturmaya yönelik bilgiler almaktadır.

Yukarıdaki cümle aslında biraz yanlış oldu. Derleyici yerine yorumlayıcı olmalıydı. Yanlış söylememin nedeni ise ancak bir yorumlayıcı oluşturarak derleyicileri daha iyi anlayacak olmanız.

Evet, bir derleyicinin nasıl oluşturulduğuna dair temel bir bilgiye sahip olmanızı ve bir derleyici oluşturmanın o kadar da zor olmadığını fark etmenizi diliyorum. İyi şanlar!

Bu bölümde herhangi bir kod yazmayacağız, eğer bazı kodları görmek istiyorsanız bu bölümü atlayabilirsiniz...

## Derleyici teorisini neden önemsemelisiniz?

Çünkü Bu **HARİKA**!

Ve çok faydalıdır. Programlar bizim için bir şeyler yapmak üzere oluşturulmuştur. Programlar, bazı veri formlarını başka bir forma çevirmek için kullanıldıklarında onlara derleyici ismini alırlar. Bu nedenle, bazı derleyici teorilerini öğrenerek, problem çözme konusunda çok güçlü bir teknikte uzmanlaşmaya çalışıyoruz. Bu senin için yeterince havalı değil mi?

İnsanlar bir derleyicinin nasıl çalıştığını anlamanın daha iyi kod yazmanıza yardımcı olacağını söylerdi. Bazıları ise, modern derleyicilerin optimizasyonda o kadar iyi olduğunu ve artık umursamamanız gerektiğini savunuyor. Bu doğru, çoğu insanın yalnızca kodun verimliliğini artırmak için derleyici teorisini öğrenmesine gerek yok. Ve çoğu insan derken seni kastediyorum!

## Biz de Teoriyi Sevmiyoruz

Derleyici teorisine her zaman hayranlık duymuşumdur çünkü programlamayı kolaylaştıran şey budur. Yalnızca Assembly dilinde bir web tarayıcısı oluşturmayı hayal edebilir misiniz? Üniversitede derleyici teorisini öğrenme şansı bulduğumda çok heyecanlandım! Ve sonra... Ne olduğunu anlamadan öğrenciliğim bitti.

Normal bir derleyici eğitimi şu konuları kapsayacaktır:

1. Söz dizimi nasıl temsil edilir (BNF vb. gibi)
2. Lexer, biraz NFA (Nondeterministik Sonlu Otomata), DFA (Deterministik Sonlu Otomata) ile.
3. Özyinelemeli iniş, LL(k), LALR vb. gibi ayrıştırıcılar.
4. Orta Seviye Diller
5. Kod üretimi
6. Kod optimizasyonu

Belki de öğrencilerin %90'ından fazlası ayrıştırıcının haricinde hiçbir şeyi umursamayacaktır, ancak bir derleyicinin nasıl oluşturulacağını hâlâ bilmiyoruz! Teorileri öğrenmek için harcadığım onca çabaya rağmen. Aslında asıl sebep, "Derleyici Thoery"nin öğretmeye çalıştığı şeyin "Ayrıştırıcı oluşturucu nasıl oluşturulur", yani sözdizimi gramerini tüketen ve sizin için bir derleyici üreten bir araç olmasıdır. lex/yacc veya flex/bison veya bunun gibi şeyler.

Bu teoriler bize derleyicilerin otomatik olarak üretilmesindeki genel sorunların nasıl çözüleceğini öğretmeye çalışır. Bu, bir kez bunlara hakim olduğunuzda her türlü gramerle başa çıkabileceğiniz anlamına gelir. Endüstride gerçekten faydalıdırlar. Yine de öğrenciler ve çoğu programcı için fazla güçlü ve fazla karmaşıktırlar. Lex/yacc'ın kaynak kodunu okumaya çalışırsanız anlayacaksınız.

İyi haber şu ki, bir derleyici oluşturmak hayal ettiğinizden çok daha kolay olabilir. Yalan söylemeyeceğim, kolay değil ama kesinlikle zor da değil.

## Bu projenin doğuşu

Bir gün Github'da [c4](https://github.com/rswier/c4) projesine rastladım . Bu proje sadece 4 fonksiyon tarafından gerçekleştirildiği iddia edilen küçük bir C yorumlayıcısıydı. En şaşırtıcı kısmı ise, önyükleme yapması (kendini yorumlayan). Ayrıca bu yaklaşık 500 satırla yapılıyor!

Bu arada derleyici hakkında pek çok ders okudum, bunlar ya çok basit (basit bir hesap makinesi uygulamak gibi) ya da otomasyon araçlarını kullanıyor (flex/bison gibi). Ancak c4 tamamen sıfırdan uygulandı. Üzücü olan şey, minimum düzeyde olmaya çalışmasıdır, bu da kodu oldukça karmaşık hale getirir ve anlaşılmasını zorlaştırır. Bu yüzden yeni bir projeye başladım:

1. Çalışan bir C derleyicisi oluştur (aslında yorumlayıcı)
2. Nasıl oluşturulduğuna dair bir eğitim yaz.

Projeyi yazmam 1 haftamı aldı, yorumlar dahil 1400 satır ortaya çıktı. Proje Github: [Write a C Interpreter'da](https://github.com/lotabout/write-a-C-interpreter) barındırılmaktadır .

Bize harika bir proje getirdiği için teşekkürler RSwier!

## Bitirmeden Önce

Bir derleyici oluşturmak sıkıcı olabilir ve hata ayıklamak zordur. Bu yüzden, kodu yazmanın yanı sıra çalışmaya da yeterince zaman ayırabileceğinizi umuyorum. Eminim siz de benim gibi büyük bir başarı duygusu hissedeceksiniz.

## Yararlı Kaynaklar

1. [Let’s Build a Compiler](http://compilers.iecc.com/crenshaw/): Yeni başlayanlar için derleyici oluşturma konusunda çok iyi bir eğitim.
2. [Lemon Parser Generator](http://www.hwaci.com/sw/lemon/): SQLite'da kullanılan ayrıştırıcı oluşturucu. Derleyici teorisini kodla anlamak istiyorsanız okumak güzel.

Umarım tadını çıkarırsın.