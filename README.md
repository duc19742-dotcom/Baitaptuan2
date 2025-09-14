using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;

namespace QuanLyHocSinh
{
    class Student
    {
        public int Id { get; set; }
        public string Name { get; set; }
        public int Age { get; set; }
    }
    internal class Program
    {
        static void Main(string[] args)
        {
            // Tạo danh sách học sinh
            List<Student> students = new List<Student>()
            {
                new Student() { Id = 1, Name = "Duc", Age = 21 },
                new Student() { Id = 2, Name = "Vu", Age = 22 },
                new Student() { Id = 3, Name = "Hop", Age = 15 },
                new Student() { Id = 4, Name = "Huong", Age = 35 },
                new Student() { Id = 5, Name = "An", Age = 17 }
            };

            // a. In toàn bộ danh sách học sinh
            Console.WriteLine("a Danh sach toan bo hoc sinh:");
            foreach (var s in students)
            {
                Console.WriteLine($"{s.Id} - {s.Name} - {s.Age}");
            }
            // b. Học sinh có tuổi từ 15 đến 18
            Console.WriteLine("\nb Hoc sinh co tuoi tu 15 den 18:");
            var tuoi1518 = students.Where(s => s.Age >= 15 && s.Age <= 18);
            foreach (var s in tuoi1518)
            {
                Console.WriteLine($"{s.Id} - {s.Name} - {s.Age}");
            }
            // c. Học sinh có tên bắt đầu bằng A
            Console.WriteLine("\nc. Hoc sinh co ten bat dau bang A:");
            var batdauA = students.Where(s => s.Name.StartsWith("A"));
            foreach (var s in batdauA)
            {
                Console.WriteLine($"{s.Id} - {s.Name} - {s.Age}");
            }

            //d. Tính tổng quát
            int tongtuoi = students.Sum(s => s.Age);
            Console.WriteLine($"\nd. Tong tuoi tat ca hoc sinh: {tongtuoi}");

            //e. Học sinh cso tuổi lớn nhất 
            int maxtuoi = students.Max(s => s.Age);
            var lonnhat = students.Where(s => s.Age == maxtuoi);
            Console.WriteLine("\ne. Hoc sinh co tuoi lon nhat:");
            foreach (var s in lonnhat)
            {
                Console.WriteLine($"{s.Id} - {s.Name} - {s.Age}");
            }
            //f. Sắp xếp theo tuổi tăng dần
            Console.WriteLine("\nf. Xap sep theo tuoi tang dan");
            var sapxep = students.OrderBy(s => s.Age);
            foreach (var s in sapxep)
            {
                Console.WriteLine($"{s.Id} - {s.Name} - {s.Age}");
            }
            Console.WriteLine();
        }
    }
}
