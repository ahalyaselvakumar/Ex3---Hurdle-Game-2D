# Ex3---Hurdle-Game-2D

## AIM:
To develop a 2D game using C# program in Unity.

## ALGORITHM:
1. Create a new project.
2. Click Content browser -> Drag the file into Unity -> Place the assets inside the viewport in Unity.
3. Define the physics properties of the objects such as the collider.
4. Assets -> Create -> # Script.
5. Create a Coding folder and create a C# file to add the coding.
6. To add our C# Script file to our selected object, click on the C# Script file drag it to our selected objects in the Hierarchy window and run the application.
7. Stop


## PROGRAM:
## Player.cs
```
using System.Collections;
using System.Collections.Generic;
using System.Security.Cryptography;
using UnityEngine;
using UnityEngine.SocialPlatforms.Impl;

public class player : MonoBehaviour
{
    public float speed;
    public float jumpforce;
    private Rigidbody2D rb;
    public Score cc;
    // Start is called before the first frame update
    void Start()
    {
        rb = GetComponent<Rigidbody2D>();
    }

    // Update is called once per frame
    void Update()
    {
        float moveinp = Input.GetAxisRaw("Horizontal");
        transform.position += new Vector3(moveinp, 0, 0) * speed * Time.deltaTime;
        if (Input.GetKeyDown(KeyCode.Space) &&Mathf.Abs(rb.velocity.y) < 0.001f)
        {
            rb.AddForce(new Vector2(0, jumpforce), ForceMode2D.Impulse);
        }
    }
    private void OnTriggerEnter2D(Collider2D other)
    { 
        if(other.CompareTag("Destroy"))
        {
            //cc.coincount++;
            Destroy(other.gameObject);
        }
    }
}
```

## Score.cs
```
using System.Collections;
using System.Collections.Generic;
using UnityEngine;
using UnityEngine.UI;
public class Score : MonoBehaviour
{
    public int coincount;
    public Text value;
    // Start is called before the first frame update
    void Start()
    {

    }

    // Update is called once per frame
    void Update()
    {
        value.text = coincount.ToString();
    }
}
```


## OUTPUT:

![image](https://github.com/user-attachments/assets/1fd7f7a1-2dfa-48ed-bcde-a77c9e5d935a)

![image](https://github.com/user-attachments/assets/fa68d71e-3a6f-4031-bf24-f35b55f46b71)


## RESULT:
Thus a 2D game using the C# program in Unity is developed successfully.


