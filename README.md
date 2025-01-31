namespace Abstract_Polimorphism
{
    internal class Program
    {
        static void Main(string[] args)
        {
            Eagle eagle = new Eagle();
            eagle.Fly();
            eagle.Eat();
            eagle.See();
            Shark shark = new Shark();
            shark.Swim();
            shark.Eat();
        }

    }
    abstract class Animal
    {
        public Animal()
        {

        }
        public abstract void Eat();
        public virtual void See()
        {
            Console.WriteLine("See as Animal");
        }
        public int MyProperty { get; set; }

    }
    abstract class Fish:Animal
    {
        public abstract void Swim();
        
    }
    abstract class Bird : Animal
    {
        public abstract void Fly();
    }
    class Eagle : Bird
    {
        public override void Eat()
        {
            Console.WriteLine("Eat as Eagle");
        }

        public override void Fly()
        {
            Console.WriteLine("fly as Bird");
        }
        public override void See()    //dinamik polimorphism
        {
            Console.WriteLine("See as Eagle ");
        }
    }
    class Shark : Fish
    {
        public override void Eat()
        {
            Console.WriteLine("Eat as Shark");
        }

        public override void Swim()
        {
            Console.WriteLine("Swim as Fish");
        }

    }
}
