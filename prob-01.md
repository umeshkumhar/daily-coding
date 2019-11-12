## Problem 01
This problem was asked by **Amazon**.

Given a string, determine whether any permutation of it is a palindrome.
For example, carrace should return true, since it can be rearranged to form racecar, which is a palindrome. daily should return false, since there's no rearrangement that can form a palindrome.

### Possible Solution

```java
package automation;

import java.io.BufferedReader;
import java.io.InputStreamReader;
import java.util.*;
import java.util.Map.Entry;

public class prob01 {
	public static void main(String args[]) throws Exception {

		BufferedReader br = new BufferedReader(new InputStreamReader(System.in));

		// read the name from the input
		String line = br.readLine();

		char[] newline = line.toCharArray();
		Boolean found = true;
		int count = 0;
		HashMap<Character, Integer> app = new HashMap<Character, Integer>();

		for (int i = 0; i < newline.length; i++) {

			if (app.containsKey(newline[i]))
				app.put(newline[i], app.get(newline[i]) + 1);
			else
				app.put(newline[i], 1);

		}

		System.out.println(app);

		int oddfound = 0;
		for (Entry<Character, Integer> e : app.entrySet()) {
			System.out.println(e.getKey() + " " + e.getValue());
			
 			if (e.getValue() % 2 == 1) {
				oddfound ++;
			} 
		}

		if (oddfound>1)
			found=false;
		else
			found =true;
		System.out.println(found);

	}
}

```


Note: Do suggest better solution. Raise a PR!
