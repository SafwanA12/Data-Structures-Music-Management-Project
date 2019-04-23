# Data-Structures-Music-Management-Project
package saf;
import java.util.Scanner;

public class LinkedListSongs 
{
Node head;

static class Node
{
	CreateSong song; 
	Node next;
	
	Node(CreateSong cs)
	{
	 song = cs;
	 next = null;
	}
}


//Inserting new node
public static LinkedListSongs addSong(LinkedListSongs list, CreateSong song) 
{ 
    
    Node new_node = new Node(song); 
    new_node.next = null; 

   
    if (list.head == null) 
    { 
        list.head = new_node; 
    } 
    else 
    { 
        
        Node last = list.head; 
        while (last.next != null) 
        { 
            last = last.next; 
        } 

        last.next = new_node; 
    } 

   
    return list; 
} 

//Method to print the LinkedList. 
public static void printPlayList(LinkedListSongs list) 
{ 
    Node currNode = list.head; 

    System.out.print("Playlist: "); 

    //traversing linkedlist
    while (currNode != null) 
    { 
       
        System.out.print(currNode.song + " "); 

        
        currNode = currNode.next; 
    } 
} 

public static void getPlayList(LinkedListSongs Playlist, CreateSong song)
{
	Scanner ip = new Scanner(System.in);
	System.out.println("Would you like to create a playlist? Say yes or no.");
	String userip = ip.nextLine();
	
	//still working on this part - anyone wiht insights is free to add 
	if(userip == "yes")
	{
		System.out.println("Please enter the songs you would like to add to your playlist.");
		String songsToAdd = ip.nextLine();
		System.out.println("When done, type 'end'.");
		//String endMarker = ip.nextLine();
		while (songsToAdd != "end")
		{
			playlist = playlist.addSong(playlist, song);
		}
		
	}
	else 
	{
		System.out.println("Thankyou.");
	}
}

public static void main (String [] args)
{
	LinkedListSongs playlist = new LinkedListSongs();
	
	CreateSong dimension = new CreateSong("4th Dimension", "Kid Cudi");
	CreateSong Alien = new CreateSong("Alien Boy", "Oliver Tree");
	CreateSong Idea = new CreateSong("Bad Idea", "Ariana Grande");
	CreateSong Alright = new CreateSong("Be Alright", "Ariana Grande");
	CreateSong Bury = new CreateSong("Bury Your Friends", "Billy Eilish");
	CreateSong Chance = new CreateSong("By Chance", "Rae Sremmurd");
    CreateSong Baby = new CreateSong("Charcoal Baby", "Blood Orange");
	CreateSong Green = new CreateSong("Collard Greens", "Schoolboy Q");
	CreateSong Money = new CreateSong("Money Longer", "Lil Uzi Vert");
	CreateSong Call = new CreateSong("One Call", "Gunna");
	CreateSong Phantom = new CreateSong("When I'm Small", "Phantogram");
	

	
	
	playlist = playlist.addSong(playlist, dimension);
	playlist = playlist.addSong(playlist, Alien);
	playlist = playlist.addSong(playlist, Idea);
	playlist = playlist.addSong(playlist, Alright);
	playlist = playlist.addSong(playlist, Bury);
	playlist = playlist.addSong(playlist, Chance);
	playlist = playlist.addSong(playlist, Baby);
	playlist = playlist.addSong(playlist, Green);
	playlist = playlist.addSong(playlist, Money);
	playlist = playlist.addSong(playlist, Call);
	playlist = playlist.addSong(playlist, Phantom);
	
	playlist.printPlayList(playlist);
	
}

