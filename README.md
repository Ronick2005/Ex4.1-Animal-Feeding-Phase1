# Ex4.1-Animal-Feeding-Phase1

## Aim:
To develop a Animal Feeding Game Phase-1 using unity.

## Algorithm:

### Player Controller:

#### Step 1:
Extract the package and in unity, asserts -> Import packages -> Custom packages and select the package. When we go to Assets folders we can see the course library which we extracted

#### Step 2:
If you want, drag a different material from Course Library > Materials onto the Ground object

#### Step 3:
Drag 1 Human, 3 Animals, and 1 Food object into the Hierarchy

#### Step 4:
Rename the character "Player", then reposition the animals and food so you can see them

#### Step 5:
Adjust the XYZ scale of the food, so you can easily see it from above

#### Step 6:
In your Assets folder, create a "Scripts" folder, and a "PlayerCtrl" script inside. Attach the script to the Player by dragging the C# file to the player and open in the inspector and check whether it is attached

### Moving Controller:

#### Step 1:
Create a new "MoveFwd" script, attach script to the Food by dragging the C# file to the food and open in the inspector and check whether it is attached

#### Step 2:
Create a new "Prefabs" folder, drag your food into Prefab folder, and a pop up raises-> choose Original Prefab

#### Step 3:
Select the Player in the hierarchy, then drag the food from your Prefabs folder onto the new Projectile Prefab box in the inspector

#### Step 4:
Rotate all animals on the Y axis accordingly to face the player

#### Step 5:
Select all three animals in the hierarchy and Add Component > Drag the Move Forward script from the Scripts into inspector

#### Step 6:
Edit their speed values and test to see how it looks. Drag all three animals into the Prefabs folder, choosing "Original Prefab"

## Program:

Name: RONICK AAKSHATH P

Reg.No.: 212222240084

#### Player Control:
```c#
using System.Collections;
using System.Collections.Generic;
using UnityEngine;

public class PlayerCtrl : MonoBehaviour
{
    public float horizontalInput;
    public float speed = 10.0f;
    public float xRange = 10f;
    public GameObject projectilePrefab;
    // Start is called before the first frame update
    void Start()
    {
        
    }

    // Update is called once per frame
    void Update()
    {
        if(transform.position.x < -xRange)
        {
            transform.position = new Vector3(-xRange, transform.position.y, transform.position.z);
        }
        if (transform.position.x > xRange)
        {
            transform.position = new Vector3(xRange, transform.position.y, transform.position.z);
        }
        horizontalInput = Input.GetAxis("Horizontal");
        transform.Translate(Vector3.right * horizontalInput * Time.deltaTime * speed);

        if (Input.GetKeyDown(KeyCode.Space))
        {
            Instantiate(projectilePrefab, transform.position, projectilePrefab.transform.rotation);
        }
    }
}
```

#### Move Forward:
```c#
using System.Collections;
using System.Collections.Generic;
using UnityEngine;

public class MoveFwd : MonoBehaviour
{
    public float speed = 40.0f;
    // Start is called before the first frame update
    void Start()
    {
        
    }

    // Update is called once per frame
    void Update()
    {
        transform.Translate(Vector3.forward * Time.deltaTime * speed);
    }
}
```
## Output:
![image](https://github.com/Ronick2005/Ex4.1-Animal-Feeding-Phase1/assets/83219341/86e72995-7412-4825-8750-12c392f06fa3)

## Result:
Animal Feeding Game Phase-1 using unity is developed successfully.
