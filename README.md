# Spawn
using System.Collections;
using System.Collections.Generic;
using UnityEngine;

public class Arrays : MonoBehaviour {

	public GameObject[] spawnPoints;

	public GameObject[] chicken;


	// Use this for initialization
	void Start () {
	
		spawnPoints = GameObject.FindGameObjectsWithTag ("Respawn");
		chicken = (GameObject)Resources.Load ("Chicken", typeof(GameObject));

		Spawn();
	}
	
	// Update is called once per frame
	void Update () {
		
	}

	void Spawn(){
		int spawn = Random.Range (0, spawnPoints.Length);

		GameObject.Instantiate (chicken, spawnPoints [spawn].transform.position, Quaternion.identity);
	}

}
