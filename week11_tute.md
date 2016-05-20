# Week 11 Tutorial

## DO EVALUATIONS 

## Objectives 
- Get you guys started on the assignment! 

## Some notes on the spec & getting started
- Make a checklist of the things it needs to do
- GUI readability and intuitiveness 
	- Does not need to be fancy; main thing is not to confuse tutors
	- Label your buttons and textboxes appropriately 
	- It should be easy to work out what to do 
	- Your GUI should scale in the sense that I should be able to see the 
	  information even when there's a lot of it; e.g., if there is a long route,
	  there shbould be, for instance, a scrollbar so I can see the whole thing
- You need to have public methods in this assignment since components of mvc
  need to talk to each other, but this does NOT mean you should just make 
  everything public; do not expose implementation details unnecessarily.
- Note that you need class invariants (and you need to protect these)! 

- Recommended sequence
	- Draw out the view 
	- Code the view 
	- Write model and controller 

## Java GUI Basics 
- Has everyone done the GUI Prac (prac 5)? If not, DO IT! 

## Model-View-Controller Pattern
- Model: knowledge; application logic. Knows nothing about UI. 
- View: ask the model for data, tell model to update itself.
- Controller: respond to events and control what the view shows by talking to 
  view and model 

## Monolithic method example
```java
/**
 * This is a method in the Wizard class which processes an attack by 
 * a wizard, directed to the characters in targets. 
 */
public void processAttack(Attack attack, List<Character> targets) {
	for(Character target : targets) {
		// See if the attack's special effect is applicable to target 
		boolean applicable = false;
		int potionBonus = 0;
		if(!target.getResistances().contains(attack.specialEffect())) {
			applicable = true;
		}
		
		if(target.getVulnerabilities().contains(attack.specialEffect())) {
			applicable = true;
		}

		if(target.getPotionEffects().contains(attack.specialEffect())) {
			applicable = true;
			potionBonus = target.getPotionEffects().potionBonus();
		}

		SpecialEffect specialEffect = attack.specialEffect();

		if(specialEffect.isType(DURATION_EFFECT)) {
			target.processDurationEffects(specialEffect);
		}

		if(specialEffect.isType(INFECTIOUS_EFFECT)) {
			for(Character nearBy : target.nearByCharacters()) {
				// Apply the effect to guys near this target
				boolean applicable = false;
				int potionBonus = 0;
				if(!target.getResistances().contains(attack.specialEffect())) {
					applicable = true;
				}
				
				if(target.getVulnerabilities().contains(attack.specialEffect())) {
					applicable = true;
				}

				if(target.getPotionEffects().contains(attack.specialEffect())) {
					applicable = true;
					potionBonus = target.getPotionEffects().potionBonus();
				}

				SpecialEffect specialEffect = attack.specialEffect();

				if(specialEffect.isType(DURATION_EFFECT)) {
					target.processDurationEffects(specialEffect);
				}
			}
		}

		if(specialEffect.isType(EASTER_EGG)) {
			Player.addAchievement(new Achievement("YOU ARE AWESOME. I LOVE WIZARDS"));
			Graphics.showUnlockedAchievement();
			LeaderBoard.update();
		}

		int damageBonus = 0;
		// Apply the actual health damage 
		if(target.getVulnerabilities.contains(weakened)) {
			damageBonus = 10;
		}

		if(attack.attackBonuses().contains(ARMOUR_BONUS)) {
			damageBonus += target.armourRating() * 0.4;
		}

		int damage = attack.baseDamage() + damageBonus;
		target.setHealth(damage);
	}
}
```
Better would be:
```java
/**
 * This is a method in the Wizard class which processes an attack by 
 * a wizard, directed to the characters in targets. 
 */
public void processAttack(Attack attack, List<Character> targets) {
	for(Character target : targes) {
		applySpecialEffects(attack, target);
		applyDamage(attack, target);
	}
}

public void applySpecialEffects(Attack attack, Character target) {
	....
	updateAchievements(....);
}

public void applyDamage(Attack attack, Character target);

public void updateAchievements(...);
```
