1.Safety ucun melumatlari istifadeciden gizletmek. Bu Istifadecinin istediyini daxil etmemesi ucun istifade olunur.

2.private - her yerde el catandir, protected - class ve classdan torendiyi class daxilinde el catandir , private-yalniz class daxilinde el catandir.
3-istifadeciye yalniz lazm olani gosteririk murekkeb prosesleri ise gizledirik. Sistemin butun detallarini bilmeden islede bilerik.

4-normal classda bir basa obyekt yaratmaq olur abstraction class ise en azindan 1 eded pure virtual funksiyasi olana deyilir, diger ferq esasen template ve ya base structure kimi istifade olunur,child class-lar həmin funksiyanı override etməlidir

5-base class daxilinde yalnız movcud olmalidir deyilen, amma implementasiyası verilmeyen virtual funksiyadır.
child class-ları mueyyen funksiyanı yazmaga mecbur etmək, ortaq interface yaratmaq ,abstraction temin etmək

6-Inheritence varislik demekdir. buda class daxilindeki method ve fildlerin diger classa otururuk ve belelikle eyni kodu bir necedefe yazmali olmuruq

7-public , public -> public , protected -> protected , private -> getmir, protected public,protected->protected ,private -> oturulmur,private, public,protected -> private kimi oturulur private oturulmur

8-eyni funksiya adi ve ya eyni cagirisi ferqli obyektlerde ferqli netice vere bilir.Compile time ve Run-
time.

9-static compile time qerar verir dynamic ise run time zamani.

10-overloading parametrlerinin sayi ve ya tiplerinin ferqli olmasinnan yaranir, overriding ise movcud olan funksiyani ezib kecmek yeniki evvel funksiya var idi ancaq biz dediyimiz kimi isleyecek.

11-funksiyanin virtual yazanda bildiririkki varislik verdiyimiz classda bu fuksyia overload olunacaq

12-child classda virtual funksiyanin duzgun sekilde yazildigini compilere bildiririk.

13-classda obyekt yaradilanda cagirilan xususi funksiyaya deyilir,default,parametrized,copy,move

14-destructor obyekt olende yeniki silinende isleyen funksiyaya deyilir, obyektin heyati sona catanda isleyir.

15-bir obyektin deyerlerini basqa bir obyekte kopyalamaga komek eden xususi constructordu, obyekt basqa bir obyekte teyin edilende.

16-this pointer — class daxilinde her metod cagirilanda avtomatik yaranan ve hemin an isleyen obyektin ozunu gosteren pointerdir, obyektin ozune muraciet etmek, memberlerle parameter adlari qarisanda ferqlendirmek ve method chaining etmek ucun istifade olunur.

17-upcasting — child (derived) class object-in parent (base) class type-e convert olunmasidir, yəni child object-in parent kimi istifade edilmesidir (Dog → Animal kimi) ve safe hesab olunur, cünki child class parent-in butun properties-lerini dasiyir, ona gore data loss olmur ve polymorphism ucun istifade olunur.

18-downcasting — parent (base) class pointer/reference-in child (derived) class type-e convert olunmasidir, yani upcasting-in tersi prosesdir (Animal → Dog kimi) ve unsafe hesab olunur, cunki parent object real olaraq child olmaya biler, ona gore yanlis conversion runtime error, undefined behavior ve ya data corruption riski yarada biler ve duzgun istifade ucun adeten dynamic_cast kimi safe checking mexanizmi teleb olunur.

19-dynamic memory allocation — runtime zamaninda memory-nin heap hissesinden dinamik olaraq ayirilmasidir, yani proqram isleyen zaman ehtiyac olduqca yaddaş yaradilir ve silinir, static memory-dan ferqli olaraq ölçü compile-time-da yox runtime-da teyin olunur.
new operatoru — heap-de memory ayirir ve obyekte yer verir, eyni zamanda constructor-u cagirira biler ve pointer qaytarir
delete operatoru — new ile ayirilmis memory-ni azad edir ve memory leak-in qarsisini almaq ucun istifade olunur, delete yazilmasa heap memory dolub sistemde problem yarada biler
yeni qisa olaraq: new memory yaradir, delete ise onu silir ve azad edir

20-Virtual destructor, bir sinifin miras aldığı zaman, miras alan sinifin destructorunun çağrılmasını təmin edən bir özelliktir. Normal bir destructor, sadece o sinifin kendi kaynaklarını temizlerken, virtual destructor sayesinde miras alan sinifin de destructoru çağrılır ve onun kaynakları da temizlenir. Bu, bellek sızıntılarını önlemek ve kaynak yönetimini düzgün yapmak için önemlidir. Eğer bir sınıfın destructorunu virtual olarak tanımlarsanız, o sınıftan türetilen herhangi bir sınıfın nesnesi silindiğinde, doğru destructor çağrılır ve tüm kaynaklar düzgün şekilde temizlenir.

21-association — class-lar arasinda en sade elaqedir, object-lar bir-birini istifade edir ama ownership yoxdur, yani biri digerine bagli deyil ve her biri musteqil yashaya bilir
aggregation — weak “has-a” elaqesidir, bir class diger class-i oz icinde referance kimi saxlayir ama ownership tam deyil, yani child object parent-dan asili deyil ve parent silinse bele child yashaya biler
composition — strong “has-a” elaqesidir, burada ownership var, yəni child object parent-in bir hissesidir ve parent silindiyi zaman child da avtomatik silinir, daha sıkı baglanti olur ve lifetime parent terefinden idare olunur

22-inheritance — “is-a” relationship yaradir, yani child class parent class-in tipidir ve onun behavior-larini miras alir, kod reuse ve polymorphism ucun istifade olunur, amma class-lar arasinda sıkı baglanti yaradir ve flexibilty azalda biler
composition — “has-a” relationship yaradir, yani bir class diger class-i oz icinde component kimi istifade edir, inheritance-dan ferqli olaraq daha fleksibl ve loosely coupled dizayn verir
inheritance daha uygun olur eger real dunya modelinde “is-a” elaqesi varsa (Dog is Animal kimi) ve polymorphism lazimdir
composition daha uygun olur eger object-lar arasinda sadece isdifade/ownership elaqesi varsa ve daha modul, deyisdirile bilen sistem qurmaq isteyirik, ve adeten modern design-da composition daha cox tercih olunur.

23-friend function — class-in private ve protected member-lerine class-in xaricinden access etmek ucun icaze verilen special function-dur, yeni class daxilinde olmadan onun gizli data-larina giris ede bilir
bu encapsulation prinsipine qismen zidd hesab olunur, çünki encapsulation data hiding demekdir, amma friend function bu gizliliyi pozaraq bir basa private member-lere access verir, buna gore adeten sadece zəruri hallarda istifade olunur (məsələn operator overloading ve ya iki class arasinda tight collaboration olduqda)

24-movcud operatoru oz isteyimize uygun islemesini yazmaqdir . (dot), :: (scope resolution), ?: (ternary), sizeof operatorlarinnan basqa butun hamisi overloading olunur

25-encapsulyasiya - tehlukesizliye inheritance - kod tekrarinin qarsisini almaqa polymorphism - eyni kodun basqa vezyetlerde basqa cur davranmasidir buda overloading ve ya overriding etmis oluruq oda error qarsisini almag komek edir abstraction -istifadeciye yalniz lazmli hisseni gosteririk belede kodu bilmeyen rahatliqla proqramdan istifade ede bilecek.
