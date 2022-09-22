# **S**tandard **T**emplate **L**ibrary
    
## Vector 
>
**Vector কি?**
>
Vector হলো *Dynamic Array*- ঠিক যতটুকু মেমরি দরকার থিক ততটুকুই নেয় । 
> 
ভেক্টর হলো একটা অ্যারে, যেটায় ডাইনামিকালি জিনিসপাতি ঢুকিয়ে রাখা যায়। মানে, এটাও একটা অ্যারে, কিন্তু সেটা ঠিক ততটুকু মেমরি খায়, যতটুকু খাওয়া লাগে।
>

ভেক্টর ডিক্লেয়ার করে এভাবে 
>
`vector< int > array;`
>
এখানে vector<variable type> এটা মূল ডিক্লেয়ার আর ``array`` হলো এখানে variable এর name ।
vector এর কয়েকটি ডাটা টাইপ হলো ঃ
>
```
vector< double > water;
>
vector< long long > balance;
>
vector< char > characters;
>
vector< day > diary;
```

> 
Vector এর একটা poperties হলো  >> `push_back()`
এটি দ্বারা vector এর শেষে একটি এলিমেন্ট যুক্ত করা যাবে। এটার কোড অনেকটে এরকম করে করা যায় ।
```
void vc(){
    int n ; cin >> n;
    vector <int> v(n);
    for(int i = 0 ; i < n; i++){
        cin >> v[i]; // এখানেই  cout << v[i] << endl; ব্যাবহার করে আউটপুট নিয়ে আসা যায় ।
    }
}
```
শেষ লুপ খেয়াল করো অনেককিছু লিখা লাগলো তাই না? কিন্তু মজার ব্যাপার হচ্ছে তুমি এতো কিছু না লিখেও পুরো একটি vector কে ইনপুট নিয়ে নিতে পারো । কোডটি দেখা যাক ;
```
void vc{
    int n ; cin >> n;
    vector<int> v(n);
    for(auto& i : v){
        cout << i << "\n"; // এভাবেও আউটপুট দেখানো যায় 
    }
}
```

অনেক Vector নিয়ে আলোচনা হলো এখন আসা যাক Stack , Queue এবং Priority -Queue নিয়ে আলোচনা করা যাক । 


## Stack
>
ধরো, তোমার মা একগাদা প্লেট ধুতে নিয়ে যাচ্ছে খাওয়ার টেবিল থেকে। সবার পরে যেটা রাখা হবে, সেই প্লেটটাকে কিন্তু সবার উপরে রাখা হবে, আর সেটাই কিন্তু সবার আগে ধোয়া হবে।

এই জিনিসটাকে বলে স্ট্যাক। মানে আমরা সবার পরে যাকে প্রসেসিং করতে ঢুকাচ্ছি তাকে যদি আগে প্রসেসিং করি তাহলে সেটাই স্ট্যাক। STL এ স্ট্যাক ব্যবহার করতে হয় এভাবে।

```
stack< int > st;
st.push( 100 ); //inserting 100
st.push( 101 ); // inserting 101
st.push( 102 ); // inserting 102
    
while( !st.empty() ) {
    cout << st.top() << endl; // printing the top
    st.pop(); // removing that one
}
```

## Queue
>
ধরো তুমি বাসের টিকেট কিনে লাইনে দাঁড়িয়ে আছো। এখন বাসে ওঠাটা হচ্ছে আমার কাজ(প্রসেসিং)। কাকে আগে বাসে উঠতে দিবে? যে সবার আগে এসেছে, তাকে। এটাকে বলে কিউ - যে সবার আগে এসেছে তাকে আগে প্রসেস করা।

```
queue< int > q;
    q.push( 100 ); // inserting 100
    q.push( 101 ); // inserting 101
    q.push( 102 ); // inserting 102
   
    while( !q.empty() ) {
        cout << q.front() << endl; // printing the front
        q.pop(); // removing that one
    }
```

## এবার আসি priority queue -এ
>
মূল কথা - এটা মাধ্যমে আমরা যেগুলো ইলিমেন্ট দেই সেগুলোই বড় থেকে ছোট আকারে পাবো। একটু ব্যাখ্যা করা যাক।
>
ধরো তুমি এক বড় অফিসে কাজ করো । প্রতিদিনের বেতন তুমি প্রতিদিনই দিয়ে দিতে পছন্দ করো । কিন্তু বেতন দেও যে কাজ করার সময়ের ভিত্তিতে , অর্থ্যাৎ যে বেশি কাজ করে সে আগে বেতন পাবে ।
দেখি কোডটা কেমন হয় ;
```
priority_queue< int > q;
q.push( 10 ); // inserting Abid
q.push( 2 ); // inserting Rahman
q.push( 4 ); // inserting Fuad 
// খেয়াল করো আমি নাম গুলো নিলাম randomly কিন্তু সংখ্যা গুলো আসবে বড় থেকে ছোট এভাবে  
   
 while( !q.empty() ) {
    cout << q.top() << endl; // printing the top
    q.pop(); // removing that one
}
```

এখন একটা বিষয়ে আলোকপাত করা যাক , আমি Stack , Queue এবং Priority -Queue এই তিনটিই আলাদা আলাদা ভাবে না বলে উপর কিন্তু এক বাক্যেই বলেছি। কিন্তু কেন?
>
আসলে এগুলোর কাজ প্রায় একই কিন্তু ব্যবহার হয় ভিন্ন ভিন্ন জায়গায় ভিন্ন ভিন্ন কারণে , মূল পার্থক্য দেখলেই পরিষ্কার হয়ে যাবে ।

প্রথমে আসি `Stack` এ;
``` 
এর কাজ হলো আমি একে প্রথমে যা দিবো সেয়া নিচে রাখবে আর পরের গুলো উপর উপর সাজাইতে থাকবে অতএব আমি শেষে যেই উপাদান দিবো সেটি সবার উপর অবস্থান করবে  
```
এবার আসি 
```
এ stack এর মতো খারাপ না এর কাছে যে আগে আসে তাকে আগেই প্রিন্ট দেয় 
```
Queue এর একটি গুরুত্বপূর্ণ properties হলো `priority Queue` 
```
এর কাজ সবচেয়ে ভালো । এর কাছে যত উপাদান আসে সে সবগুলোকে দেখে নেয় । তারপর সাজায় নেয় অর্থ্যাৎ যে বেশি সম্মানের [যার priority বেশি বা সরাসরি বলতে গেলে যে বড়] তাকে সবার উপরে জায়গা দেয়
```


Code এবং বেশিরভাগ কথা [এখান](http://www.progkriya.org/gyan/stl.html#section12) থেকে নেওয়া । 