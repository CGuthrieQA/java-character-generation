# Chargen in Java

This is the fist thing I made in java, it rolls 3d6 down the line.

```java
// This rolls 3d6 down the line for D&D statistics.

package com.qa.main;

import java.util.Random; // import random

public class Runner {
	
	// roll a D6
	public static int rollD6() {
		
		// create new random instance of class Random
		Random ran = new Random();
		
		// random number between 0 and 5 (+1)
		int roll = ran.nextInt(6) + 1;
		
		// return value of roll
		return roll;
		
	}
	
	// roll 3 D6
	public static int roll3D6() {
		
		// total of rolls
		int total = 0;
		
		// i variable to loop
		int i;
		
		// loop 3 times (once per d6)
		for ( i = 0; i < 3; i++ ) {
			
			// add d6 to the total
			total += rollD6();
			
		}
		
		//return the total number
		return total;
		
	}
	
	// Generate a character
	public static void charGen() {
		
		// statistics variable
		String[] stats = {"STR", "DEX", "CON", "INT", "WIS", "CHA"};
		
		// i variable to loop
		int i;
		
		// loop through statistics array 
		for (i = 0; i < stats.length; i ++) {
			
			//print the array item followed by a space followed by the result of rolling 3d6
			System.out.println(stats[i] + " " + roll3D6());
			
		}
		
	}

	public static void main(String[] args) {
		
		// do the thing!
		charGen();
		
	}

}

```