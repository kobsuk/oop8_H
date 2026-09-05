export{}
abstract class Monster {
  constructor(public name: string, public health: number) {}
  damage(): number {
    return 10;
  }
  abstract attack(): void;
}

class FireMonster extends Monster {
  attack(): void {
    console.log(`${this.name} attacks with fire, causing ${this.damage()} damage! fire`);
  }
}

class WaterMonster extends Monster {
  attack(): void {
    console.log(`${this.name} attacks with water, causing ${this.damage()} damage! water`);
  }
}

class GrassMonster extends Monster {
  attack(): void {
    console.log(`${this.name} attacks with grass, causing ${this.damage()} damage! grass`);
  }
}
function battleArena(monsters: Monster[]): void {
  monsters.forEach(monster => monster.attack());
}


const monsters: Monster[] = [
  new FireMonster("Blaze", 100),
  new WaterMonster("Aqua", 120),
  new GrassMonster("Leafy", 90)
];

battleArena(monsters);
