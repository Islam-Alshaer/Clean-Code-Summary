# مقدمة صاحب الملخص : 
  هذا الملخص مقدم لكم برعاية if else boys بواسطة اسلام 
## اخلاء مسئولية 
- هذا الملخص يعبر بالضرورة عن *فهمي الشخصي* والذي قد يخطء في بعض المسائل 
- هذا الملخص **لا يغني اطلاقا عن قراءة الكتاب نفسه**, خصوصا مع توافر الامثلة المطروحة فيه 
- الهدف الوحيد من هذا الملخص هو تسهيل الامر لدى المبرمجين الذين قد لا يملكون الوقت الكافي لقراءة الكتاب
- الأمثلة المذكورة في هذا الملخص أغلبها -ان لم يكن كلها- هي من صنعي الشخصي لتسهيل المسائل للقارئ, وهي مستوحاة من محتوى الكتاب
- وهذا يعني انه يعتبر كبسولة سريعة الهضم او مكمل غذائي, *وليس وجبة مشبعة من المعلومات*
- لا يسمح بنشر او تداول هذا الملخص قبل *الصلاة على النبي* ثم **الدعاء لاهل غزة**, أسال الله ان يرفع عنهم البلاء وأن ينصرهم نصرا عزيزا مؤزرا, وأن يرزقهم الصبر والثبات وأن يربط على قلوبهم ويثبت أقدامهم ويسدد رميهم ويجعلهم اية لنصره, وأن يهلك عدوهم, 
  اللهم منزل الكتاب ومجري السحاب هازم الاحزاب اهزم اليهود وانصرنا عليهم 
## يرجى قراءة الملخص في صيغة md كلما أمكن ذلك
## لا تنسونا من صالح دعائكم أنا وشباب if else boys
## يرجى تنبيهي عند اكتشاف أخطاء علي ال email الاتي : 
- islam.alsha3er.3@gmail.com
# Clean Code
author provides some general concepts and guidelines to writing code before diving into details 
## Good Code matters
- الوحدة الوحيدة لقياس جودة الكود هي **حوقلة/دقيقة** (لا حول ولا قوة الا بالله, اي يبني الكود دا!)
- with bad code, team's productivity decreases
- and due to that team tries hard to increase thier productivity
- which leads to even worse code, because team are just focusing on "getting it done"
- when developers are on the pressure on delivering code before deadlines, code becomes sloppy, to the point it becomes hopless and they realise they need to redo the whole project
- and then a team of the best developers is gathered
- the tiger team must build a new system, parallel to the old team 
- tiger team is now requested not only to redo the whole project, but to catch up with the changes happening to the original team
- time passes, and tiger team realises their code has become with time no better than the old one!!!
- those races may continue for 10 long years, for absloutly nothing !
- Clean code helps in :
	- maintanance
	- modifications
	- readabillity
	- minimizing number of errors and bugs
	- saving time
## Attitude 
- من مسئوليتك العلمية والمهنية انك تكون صادق مع المدير 
	- لو الشغل هياخد شهر, متقولش 3 اسابيع, قول شهر
	- الموضوع عامل زي الجراح اللي المريض قاله "بلاش تعقيم قبل العملية, تضييع وقت على الفاضي"
	  لو الدكتور سمع كلامه, يبقا أذاه, هنا المريض جاهل فمن مسئولية الطبيب انه يوعيه ويصارحه
- clean code infact make you FASTER not slower, in the long term
# Chapter 1 : What is clean code 
### Stroustrup
	I like my code to be elegant and effiecient. The logic should be straightforward to make it hard for bugs to hide, the dependencies minimal to ease maintenance, error handling complete according to an articulated strategy, and performance close to optimal so as not to tempt people to make the code messy with unpricipled optimizations. "Clean code does one thing well". 
### Grady Booch
	Clean code is simple and direct. Clean code reads like well-written prose. Clean code never obscures the designer's intent but rather is full of crisp abtractions and straight forward line of control.
	*clean code should contain only what is neccessary*
### Dave Thomas
	Clean code can be read and  enhanced by a developer other than its original author. It has unit and acceptance tests. It has meaningful names. "It provides one way rather than many ways for doing the same thing". It has minimal dependencies, which are explicitly defined, and provides a clear and minimal API. Code should be literate since depending on the language, not all necessary information can be expressed clearly in code alone.
### Michael Feathers
	Clean code is always looks like it was written by someone who cares. There is nothing you can do to make it better 
### Ron Jiffries
	In priority of order, simple code : 
	- runs all tests
	- contains no duplications
	- Expresses all the design ideas that are in the system 
	- Minimizes the number of entities such as classes, methods and functions.
### Ward Cunningham 
		You know you are working on clean code when each routine you read turns out to be pretty much what you expected. You can call it beautiful code when the code also makes it "look like the language was made for the problem"
### The Boy Scout Rule
**Leave the camp cleaner than you found it


#  Chapter 2: Meaningful names
- it's exteremely important
### Use intention revealing names
- use the unit itself inside variabl's name, for example:
	- int elapsedTimeInDays;
	- int daysSinceCreation;
	- int fileAgeInDays;
- if a name requires a comment then the name does not reveal its intent, for example:
	- int d; //number of books available
```cpp
for(int i = 0; i < 2; i++){
	if(arr[i][i] != arr[i + 1][i + 1]){
		y = false;
	}
}
```
the problem isn't the simplicity of the code but the *implicity* of the code.
- compare the last code with this one : 

```cpp
for(int cell_index = 0; cell_index < diagonal_size - 1; cell_index++){
	int cell = board[cell_index][cell_index];
	int next_cell = board[cell_index + 1][cell_index + 1];
	if( cell != next_cell)
		player_wins = false;
}
```

### Avoid disinformation:
- do not refer to a grouping of books as BooksArray unless it's actually an array!
	- if it's a vector, that would make a great confusion to the reader
- خليك حذر في استخدام الاسماء المتشابهة : 
	- XYZControllerForEfficientHandlingOfStrings
	- XYZControllerForEfficientStorageOfStrings
		- prgrammers use autocompletion, that would make a problem if names arn't easy to be distinguished from each other
- avoid using lower case 'l' or uppercase "I" or uppercase O as variable names
- consider following code :
```cpp
int a = l;
if(O == l)
	a = O1;
else
	l = O1;
```
### make meaningful distinctions
- number series naming (a1, a2...aN) is the opposite of intentional naming
- Noise words are meaningless distinctions:
	- what is the differance between : ProductInfo and ProductData ???
	- you made variable names differant without them meaning actually something differant
### use pronouncable names
- name like : 
	- BkDta for : BookData 
	- plyr for : player
	- rgstr for : register
- those are non-pronouncalbe and consequently we can't discuss them in a programming enviroment without sounding like idiots
- programming is something done between people, which mean it needs to be communicated properly in meetings and discussions 
### use searchable names 
- a length of a name should correspond to the size of its scope
- a name like "e" is a bad choice for a variable that is used in multiple places in code body, it's the most frequent letter in English
	- trying to search for it will cause you to go through jungles of strings and code lines to reach it 
### Avoid Econdings
### Avoid metal mapping 
- don't show off your mental abillity by naming variables with one character and mapping that character in your head to it's actual meaning 
### Class name 
- should be a noun, like Customer, WikiPage, AddressParser.
- avoid names like Manager, Processor, Data, Info in the name of a class 
### Method names
- methods should have verb or verb phrase names like : deletePage or save.
- WHEN constructors are overloaded, use static factory methods with names that describe the arguments, for example 
	- Complex x = Complex.FromRealNumber(23.0);
		> static factory vs abstract factory here : 
### Don't be cute
- انك تسمي اسماء زي nine11 عشان توصف ال destructor بتاع الكلاس tower مثلا حاجة هتخلي الكود غير مقروء وغير منطقي للمبرمج اللي هيشتغل بعدك 
### Pick one word per concept 
- be consistant with your naming style 
	- يعني مثلا ميبقاش fetch و retrieve و get بيعملو نفس الحاجة في classes مختلفة 
	- اختار اسم واحد فيهم لمبدأ ما ووحد الاستخدام دا في كل حتة في الكود '
	- استخدم add مثلا لجمع قيمتين, وعليه **متستخدمش** اسم add عشان تضيف عنصر ل set of elements مثلا 
### Use Solution domain names
- استخدم مصطلحات ال CS للمشاكل المعروفة والمشهورة زي ال dijkstra مثلا او fourier series او اسماء ال data structures زي ال queue و ال stack و ال hash map وغيره
- استخدم مصطلحات الحاجة اللي شغال فيها, يعني لو بتعمل برنامج لتنظيم تخزين المواد الكيميائية بين مجموعة من المعامل, استخدم المصطلحات الكيميائية اللي تعرفها وليها علاقة ببرنامجك, زي ان المادة ليها درجة حرارة ب "تتسامى" عندها او غيره 
### Add meaningful context
- لو شفت اسماء زي board, player, score, choice, ممكن تتوقع ان احنا بنحاول نعمل لعبة
	- بس لو شفت كلمة choice لوحدها, هل كان هيجيلك نفس الانطباع ؟
	- وبالتالي بيكون كويس انك تضيف prefix للاسم عشان تدي سياق : 
		- game_board, player_choice, player_score 
	- take a look at this java code 
```java
private void printGuessStatistics(char candidate, int count) {     
	String number;
    String verb;
    String pluralModifier;
    if (count == 0) {
      number = "no";
      verb = "are";
      pluralModifier = "s";
    } else if (count == 1) {
      number = "1";
      verb = "is";
      pluralModifier = "";
    } else {
      number = Integer.toString(count);
      verb = "are";
      pluralModifier = "s";
    }
    String guessMessage = String.format("There %s %s %s%s", verb, number, candidate, pluralModifier);
    print(guessMessage);   
}	
```

now compare with this one : 
```java
public class GuessStatisticsMessage {
  private String number;
  private String verb;
  private String pluralModifier;
  
  public String make(char candidate, int count) {
    createPluralDependentMessageParts(count);
    return String.format("There %s %s %s%s",verb, number, candidate, pluralModifier);
  }
  
  private void createPluralDependentMessageParts(int count) {     
    if (count == 0) {
      thereAreNoLetters();
    } else if (count == 1) {
      thereIsOneLetter();
    } else {
      thereAreManyLetters(count);
    }
  }
  
  private void thereAreManyLetters(int count) {     
	number =  Integer.toString(count);
    verb = "are";
    pluralModifier = "s";
  }
  
  private void thereIsOneLetter() {     
    number = "1";
    verb = "is";
    pluralModifier = "";
  }
  
  private void thereAreNoLetters() {     
    number = "no";
    verb = "are";
    pluralModifier = "s";   }
}
```

### بلاش مبدأ أبو بلاش كتر منه 
- in an application called "gas station deluxe" it's a bad idea to prefix every class with GSD
	- لما تيجي تبحث عن اسم هيبقا صداع
- shorter names are usually better than long ones
- add no more context to a name than is neccessary 
# chapter 3 : Functions
