# -timer.schedule
 timer.schedule计时器的用法，以及开启子线程——例子，点击两下返回键退出app

 需求：第一次点击返回键，提示：再次点击退出，在2秒内第二次点击，退出app，若超过了2秒，则还是看作是第一次点击，提示再次点击退出。
 在方法onBackPress()方法里面进行操作
 
     private Boolean first_enter=true;
       public void onBasePress(){
         if(first_enter==true){
         //第一次进入
            first_enter=false;
            Toast.makeText(MainActivity.this,"再次点击退出",Toast.LENGTH_SHORT).show();

            Timer timer=new Timer();
            timer.schedule(new TimerTask(){
               public void run(){
                  first_enter=true;
               }

            },2000);

        }else{
         finish();

        }
        }



