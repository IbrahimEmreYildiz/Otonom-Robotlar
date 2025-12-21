# Otonom-Robotlar
Otonom Mobil Robot Navigasyonu ve SLAM Projesi
Bu proje, ROS (Robot Operating System) Noetic ortamında, Gazebo simülatörü kullanılarak geliştirilmiş bir otonom navigasyon ve haritalama (SLAM) çalışmasıdır. Robot, karmaşık bir ortamda (7-8 adet engel) kendi yolunu planlayabilmekte ve eş zamanlı olarak çevresinin haritasını çıkarabilmektedir.

📺 Proje Videosu
VİDEO LİNKİ: https://youtu.be/aqQFxjvh7aA

🚀 Öne Çıkan Özellikler
SLAM (Gmapping): Lazer tarayıcı verileri kullanılarak gerçek zamanlı 2B doluluk haritası (Occupancy Grid Map) oluşturulmuştur.

Otonom Navigasyon (Move Base): Global ve Local planlayıcılar ile dinamik engel kaçınma gerçekleştirilmiştir.

Lidar Optimizasyonu: Robotun kendi gövdesini engel olarak algılamasını önlemek amacıyla min_range değeri 0.30m olarak optimize edilmiştir.

Güvenli Sürüş: inflation_radius (şişirme yarıçapı) ayarları ile robotun dar geçişlerden (kutuların arasından) güvenli bir şekilde geçmesi sağlanmıştır.

🛠 Kullanılan Teknolojiler
İşletim Sistemi: Ubuntu 20.04 (Focal Fossa)

ROS Dağıtımı: Noetic

Simülasyon: Gazebo

Görselleştirme: RViz

📋 Kurulum ve Çalıştırma
Projeyi kendi yerel makinenizde çalıştırmak için aşağıdaki adımları sırasıyla takip edin:

1. Çalışma Alanını Derleme
Bash

cd ~/catkin_ws
catkin_make
source devel/setup.bash
2. Simülasyonu Başlatma (Gazebo)
Bash

roslaunch my_robot_description spawn_robot.launch
3. Haritalama ve Navigasyon Düğümleri
Her bir komutu ayrı bir terminalde ve source yaptıktan sonra çalıştırın:

Bash

# SLAM Gmapping
roslaunch my_robot_description gmapping.launch

# Navigasyon (Move Base)
roslaunch my_robot_description move_base.launch

# Görselleştirme (RViz)
rosrun rviz rviz
📐 Teknik Detaylar
Sunum sırasında vurgulanan temel mühendislik çözümleri:

Tekerlek Yapısı: Diferansiyel sürüş sistemi (Differential Drive).

Maliyet Haritası: Dinamik olarak güncellenen Global ve Local Costmap yapıları.

Sensör Füzyonu: Odometri verileri ve Lazer tarama verilerinin Gmapping üzerinden birleştirilmesi.

👤 Hazırlayan
İsim Soyisim: [İbrahim Emre YILDIZ]

Bölüm: Bilgisayar Mühendisliği 

Öğrenci No: 2020555069
