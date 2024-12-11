import java.util.*;
public class Slink
{
    class node{
        int data;
        node next;
        node(int data)
        {
            this.data=data;
            next=null;
        }
    }
    node head1=null,temp1=null;
    node head2=null,temp2=null;
    public void insert1(int data){
        node newnode=new node(data);
        if(head1==null)
        {
            head1=newnode;
            temp1=newnode;
        }
        else
        {
            temp1.next=newnode;
            temp1=newnode;
        }
    }
    public void insert2(int data){
        node newnode=new node(data);
        if(head2==null)
        {
            head2=newnode;
            temp2=newnode;
        }
        else
        {
            temp2.next=newnode;
            temp2=newnode;
        }
    }
    int compare()
    {
        node temp1=head1;
        node temp2=head2;
        int c1=0,c2=0,flag=0;
        while(temp1!=null){
            c1++;
            temp1=temp1.next;
        }
        while(temp2!=null){
            c2++;
            temp2=temp2.next;
        }
        if(c1!=c2)
            return 0;
        else{
            temp1=head1;
            temp2=head2;
            while(temp1!=null)
            {
                if(temp1.data!=temp2.data)
                {
                    flag=1;
                    break;
                }
                else
                {
                    temp1=temp1.next;
                    temp2=temp2.next;
                }
            }
            if(flag==1)
                return 0;
            else
                return 1;
        }
    }
	public static void main(String[] args)
	{
	    Scanner sc=new Scanner(System.in);
	    Slink X=new Slink();
	    int t=sc.nextInt();
	    int n=0,m=0,data1=0,data2=0;
	    for(int i=0;i<t;i++)
	    {
	        n=sc.nextInt();
	        for(int j=0;j<n;j++)
	        {
	           data1=sc.nextInt();
	           X.insert1(data1);
	        }
	        m=sc.nextInt();
	        for(int j=0;j<m;j++)
	        {
	           data2=sc.nextInt();
	           X.insert2(data2);
	        }
	        int res=X.compare();
	        System.out.println(res);
	    }
	}
}
