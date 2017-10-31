# Smart_Glasses
A tool which intends to help for blind people. Consists of Text Recognition and Face Recognition features.

The only way a visually impaired person reads is by using a special writing system called Braille,  named after the developer Louis Braille. In this system, each character is made by putting a special pen on a slate with rectangular boxes called cells, each of which can raise the cells and their combination makes different characters. But this approach has a lot of practical shortcomings. Braille as a script requires its own equipment. It requires an embossed paper and the above mentioned slate. Course books and other reading material must all be braille printed, which is expensive. Also not all books have their copies in braille. Braille requires trained professionals to translate their written thoughts and to tell what they have written. 

Therefore, even after being one of the most elegant solution of its time, it is not able to overcome these, so we have come up with a technological innovation that lets visually impaired people read English script. How do we do that? By means of text-to-speech technology. Once the person knows what is to be read, the camera is focussed, which captures the image and written (printed) text is converted into speech which the person can then hear. Since this is mainly for printed texts, it is computationally feasible. Now the person can read road signs and directions, books, newspaper, price on grocery items, number plates, and so on, independently. All this is using a Raspberry pi, camera and audio jack. This proves out to be a cheap and an elegant solution. 

How do we achieve this? We use OpenCV, a library for image analysis, and detect the edges of the paper that we want to read. Then we do some image correction to adjust the brightness and contrast of the image such that the text part is completely visible and the page part is made white. All this is done so that tesseract, a software for the conversion of the image to text, can process the image and convert it’s content to text. Such types of softwares work on the principles of Optical Character Recognition. The text is then passed to any standard text-to-speech softwares (like eSpeak in our case), which renders the text to audio which the person can easily hear. This sounds quite tedious but we have developed a working prototype of the same. The solution is quite cost effective (considering the cost of an RPi and RPi camera). Everything is then compactly put in the form of a “cap like glasses”. The system needs only the power source of the RPi and nothing else which means no Internet!.

Once we had added the camera along with a strong microcomputer like RPi, we thought of using it to our advantage. So we went ahead and thought of the next major problem faced by visually impaired people, the difficulty that they face in order to freely interact with a person. Hence we integrated facial recognition to our initial prototype. Visually impaired people now have to depend on no one for recognising people, since the project is capable of saving new faces and also recognise the old ones. It uses OpenCV’s LBPH FaceRecognizer to train on image dataset from Yale. Once trained it takes an input from the Raspberry Pi’s camera and add depending whether it is able to recognize the image or not, it places in training images so that it can identify such face in future or correctly predicts the familiar face. Given that in any normal interaction people generally face each other to interact, we used Haar Cascades frontal face features to train our model on. The algorithm is simple but offers a very elegant solution to the ones who actually need it the most.

