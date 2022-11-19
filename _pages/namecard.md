---
permalink: /namecard/
title: "Tomoki Ishibashi, Ph.D. / 石橋朋樹 博士(理学)"
author_profile: true
---

<script type="text/javascript">
function convertLetter5_shtml(t, p){
var s = "", letter = "";
for(var i = 0; i<t.length; i++){
letter = t.charCodeAt(i);
s += String.fromCharCode(letter + p);
}
return s;
}
var em_shtml1 = convertLetter5_shtml(String.fromCharCode(111, 106, 104, 106, 102, 100, 41, 100, 110, 99, 100, 93, 92, 110, 99, 100)+String.fromCharCode(59, 109, 100, 102, 96, 105, 41, 101, 107), 5);
var em_shtml2 = convertLetter5_shtml(String.fromCharCode(101,110,107,101,110,107,112,107,105,107,103)+String.fromCharCode(101,60,99,105,93,101,104,42,95,107,105), 4);
var ph_shtml1 = convertLetter5_shtml(String.fromCharCode(40,53,46,42,45,50,45,42,48,50,45,47,42,50,54,49,47), 3);
var ph_shtml2 = convertLetter5_shtml(String.fromCharCode(40,53,46,42,45,54,45,42,46,51,52,50,42,45,49,48,45), 3);

document.write("Business e"+"-"+"m"+"ail a"+"ddr"+"es"+"s: <a href=\"ma"+"ilt"+"o:"+em_shtml1+"\">"+em_shtml1+"</a><br>");
document.write("Private e"+"-"+"m"+"ail a"+"ddr"+"es"+"s: <a href=\"ma"+"ilt"+"o:"+em_shtml2+"\">"+em_shtml2+"</a><br><br>");
document.write("Business p"+"hon"+"e nu"+"mbe"+"r: " + ph_shtml1 + "<br>");
</script>
<noscript><img src="/images/mailto.png"></noscript>

---
 
{% for experience in site.experiences %}{% assign exp=experience %}{% endfor %}

住所: <a href="{{ exp.address_url_j }}" target="_blank" rel="noopener noreferrer">{{ exp.address_j }}</a>

Address: <a href="{{ exp.address_url }}" target="_blank" rel="noopener noreferrer">{{ exp.address }}</a>

---

名前: <b><u>石橋朋樹</u></b>

Name: <b><u>Tomoki Ishibashi</u></b>

---

学位: [博士(理学)](../images/学位記.jpg)

Degree: [Ph.D.](../images/学位記.jpg)

---

所属: <a href="{{ exp.venueurl }}" target="_blank" rel="noopener noreferrer">{{ exp.institute_j }} {{ exp.dept_j }} {{ exp.lab_j }}</a>

Affiliation: <a href="{{ exp.venueurl }}" target="_blank" rel="noopener noreferrer">{{ exp.lab }}, {{exp.dept }}, {{exp.institute }}</a>

---

職位: {{ exp.title_j }}

Position: {{ exp.title }}

---

名刺からジャンプいただきありがとうございます．

最近，「もっとキツい性格の人だと思っていた」と言われることが増えてきたのですが，実際のところ，浮かれポンチの超極楽トンボ (極楽のさらに上，「超極楽」の運動場を整地するために使われるトンボのこと) として生きているので警戒は不要です．
 
あと，とても重要なことなのですが，好きなバンドは[鈴木実貴子ズ](https://www.youtube.com/watch?v=uQkddcoMLbg&list=PLGFcgF89YT2L1YgQZt4k31XLdYKWKQfES)です．学生時代からずっと応援しているバンドで，鈴木実貴子ズの話を聴いて彼女らの話さえしてもらえれば私はだいたいゴキゲンになります．

今後とも，よろしくお願い申し上げます．

---

<script src="https://utteranc.es/client.js"
        repo="ishibaki/ishibaki.github.io"
        issue-term="title"
        theme="github-light"
        crossorigin="anonymous"
        async>
</script>
