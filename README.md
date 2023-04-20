# CSharp-Dosyalama-Islemleri-

C# Dilinde Dosyalama İşlemleri
 Dosyalama işlemleri klasör ve dosya işlemleri olmak üzere ikiye ayrılır. Bu işlemler yapılırken
programın başına “using” anahtar sözcüğünden sonra “System.IO” ön işlemcisi eklenmelidir. 

Klasör işlemlerinde sıklıkla “Directory” sınıfı, dosya işlemlerinde ise “File” sınıfı tercih edilir. Her iki sınıfta
da kullanılan metoda bağlı olarak verilen parametre değeri ve bu parametrenin oluşturacağı yol
daima string şeklinde ve (@"...") olarak verilmelidir.
# 1. Klasör İşlemleri
# a. Klasör Oluşturmak
 Directory sınıfını kullanarak klasör oluşturmak için “CreateDirectory” komutunu kullanırız.
Directory.CreateDirectory(@"C:\Ornek"); // Ornek adında bir klasör oluşturur.
# b. Klasör Silmek
 Directory sınıfını kullanarak klasör silmek için “Delete” komutunu kullanırız.
Directory.Delete(@"C:\Ornek"); // Ornek adındaki klasörü siler.
 Yukarıdaki komut satırında klasörün bulunamaması veya klasörün içi dolu olma durumunda hata ile
karşılaşılabilir. Bu durumda “false” komutu eklenerek silme işlemi iptal edilir.
Directory.Delete(@"C:\Ornek", false);
// Ornek klasörünün içerisi boş olmadığı için işlem iptal edilir.
 Eğer ki içi dolu olan bir klasör silinecekse “true” komutu eklenir. Böylece ilgili klasörün içi boş da
olsa dolu da olsa her şekilde silinecektir.
Directory.Delete(@"C:\Ornek", true);
# c. Klasör Kontrolü
 Klasörün bulunup bulunmadığını kontrol eden bu metot eğer ki klasörü bulursa “true”, bulamazsa
“false” değerini geri döndürür.
Directory.Exists(@"C:\Ornek");
# d. Klasör Taşımak
 Bir klasörü başka bir klasörün içerisine taşımak için kullanılır. En az iki parametre içermelidir.
Directory.Move(@"C:\Users\Ornek", @"C:\Desktop\Deneme");
// Taşınacak klasörün yolu , Taşınacak yerin yolu
# e. Klasör Listelemek
 Bir klasörün içerisindeki klasörleri listelemek için kullanılır.
Directory.GetDirectories(@"C:\");
string [] klasorler = Directory.GetDirectories(@"C:\");
foreach (string klasor in klasorler)
{
 Console.WriteLine(klasor);
}
# 2. Dosya İşlemleri
# a. Dosya Oluşturmak
 Dosya oluşturmak için kullanılır. Dosya uzantısı değiştirilerek farklı tipte dosyalar oluşturulabilir.
File.Create(@"C:\Ornek\deneme.txt");
# b. Dosya Silmek
File.Delete(@"C:\Ornek\deneme.txt");
# c. Dosya Kontrolü
 Dosyanın bulunup bulunmadığını kontrol eden bu metot eğer ki dosyayı bulursa true, bulamazsa
false değerini geri döndürür.
File.Exists(@"C:\Ornek\deneme.txt");
# d. Dosya Taşımak
 Bir dosyayı başka bir klasörün içerisine taşımak için kullanılır. En az iki parametre içermelidir.
File.Move(@"C:\Ornek\deneme.txt", @"C:\Masaustu\Proje.txt");
// Taşınacak dosyanın yolu , Taşınacak yerin yolu
// Deneme.txt dosyası taşınan klasöre Proje.txt adıyla taşınır.
# e. Dosya Kopyalamak
File.Copy(@"C:\Ornek\deneme.txt", @"C:\Masaustu\Proje.txt");
 Hedef adreste aynı isme sahip dosya varsa hata ile karşılaşılır. Aynı isimli dosya bulunduğunda
verileri üzerine kaydetmek için “true” komutu eklenir, işlemden vazgeçmek için “false” komutu
eklenir.
File.Copy(@"C:\Ornek\deneme.txt", @"C:\Masaustu\Proje.txt", true);
