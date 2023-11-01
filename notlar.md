/boot/efi bölümü, UEFI (Unified Extensible Firmware Interface) önyükleme sürecinde kullanılır. Bu bölüm, UEFI firmware tarafından kullanılan önyükleme yükleyicilerini içerir. UEFI, BIOS'un yerini alan daha modern bir firmware'dir. BIOS'un aksine, UEFI, 2 TB'den büyük diskler ve GPT (GUID Partition Table) gibi yeni disk bölümleme sistemlerini destekler ²³ .

LVM (Logical Volume Manager), disk bölümlerini yönetmek için kullanılan bir araçtır. LVM, disk bölümlerinin boyutunu dinamik olarak değiştirmeyi ve birden fazla diski tek bir mantıksal birim olarak birleştirmeyi mümkün kılar. LVM, /boot/efi bölümünün LVM grubu dışında ayarlanması gerektiğini belirtir ¹. Bu nedenle, /boot/efi bölümü LVM grubu dışında ayarlanmalıdır.

/boot/efi bölümünün boyutu, kurulumun yapıldığı sisteme bağlı olarak değişebilir. Ancak genellikle 100 MB veya daha fazla olması önerilir ¹. Bu boyut, UEFI firmware tarafından kullanılan önyükleme yükleyicilerinin depolanması için yeterli olacaktır.
/tmp dizini, Linux işletim sistemlerinde **geçici dosyaları** içerir. Programlar tarafından oluşturulan geçici dosyalar burada saklanır. /tmp bölümü genellikle RAM diskinde bulunur ve her önyüklemede temizlenir ¹.

/tmp bölümü için **ext2 dosya sistemi** seçilmesinin nedeni, ext2'nin basit ve güvenilir olmasıdır ¹. Ayrıca, ext2 dosya sistemi, /tmp bölümü için en uygun seçenek olarak kabul edilir ¹. Bunun nedeni, ext2'nin sadece temel özellikleri içermesi ve bu özelliklerin /tmp bölümü için yeterli olmasıdır.

Linux işletim sistemlerinde, disk bölümleri, farklı amaçlar için kullanılır. İşte bu disk bölümlerinin bazıları ve amaçları:

- **/root**: Bu dizin, Linux sistemindeki **root kullanıcısının ev dizinini** içerir. Root kullanıcısı, Linux sistemindeki en yüksek yetkilere sahip kullanıcıdır. Bu dizin, root kullanıcısının kişisel dosyalarını, yapılandırma dosyalarını ve diğer sistem dosyalarını içerir. Root kullanıcısı, sistemin tüm dosyalarına erişebilir ve değiştirebilir. Bu nedenle, /root dizini sadece root kullanıcısı tarafından erişilebilir ¹.

- **/home**: Bu dizin, Linux sistemindeki **normal kullanıcıların ev dizinlerini** içerir. Her normal kullanıcı, kendi ev dizinine sahiptir. Bu dizinler, normal kullanıcıların kişisel dosyalarını ve yapılandırma dosyalarını içerir ¹.

- **/srv**: Bu dizin, Linux sistemindeki **sunucu verilerini** içerir. Örneğin, web sunucusu veya FTP sunucusu gibi sunucuların verileri burada saklanır ¹.

- **/tmp**: Bu dizin, Linux sistemindeki **geçici dosyaları** içerir. Programlar tarafından oluşturulan geçici dosyalar burada saklanır. /tmp bölümü genellikle RAM diskinde bulunur ve her önyüklemede temizlenir ¹.

- **/var**: Bu dizin, Linux sistemindeki **değişken verileri** içerir. Örneğin, log dosyaları veya veritabanı dosyaları gibi değişken veriler burada saklanır ¹.

- **/var-log**: Bu dizin, Linux sistemindeki **log dosyalarını** içerir. Log dosyaları, sistem olaylarını kaydeder ve hata ayıklama için kullanılır ¹.

- **swap**: Swap bölümü, Linux işletim sistemlerindeki **sanal bellek alanını** temsil eder. Swap bölümü, RAM'in dolu olduğu durumlarda kullanılır. Swap bölümüne yazılan veriler sabit diske yazılır ve daha sonra okunabilir ¹.

Fedora, varsayılan olarak **Btrfs dosya sistemi** kullanır ¹. Btrfs, birçok özellik sunar, örneğin şunlar:

- **Sıkıştırma**: Btrfs, verileri sıkıştırarak diskte daha az yer kaplamasını sağlar ¹.
- **Snapshot**: Btrfs, anlık görüntüleme özelliği sunar. Bu özellik, sistemdeki bir dosya veya dizinin anlık görüntüsünü almanızı sağlar. Bu özellik, sistemdeki bir hata durumunda dosyaların kurtarılmasına yardımcı olabilir ¹.
- **RAID**: Btrfs, RAID 0, RAID 1 ve RAID 10 gibi farklı RAID seviyelerini destekler ¹.

Ancak, disk bölümlerinin Btrfs olarak ayarlanması, sisteminize bağlıdır. Örneğin, disk bölümlerinizin boyutu ve kullanım amacı gibi faktörler bu kararı etkileyebilir. Bu nedenle, disk bölümlerinin Btrfs olarak ayarlanması gerekip gerekmediğine karar vermek için ihtiyaçlarınızı ve gereksinimlerinizi dikkate almanız gerekir.
