# My Streamlit project overview

Initially creating this as a portfolio website in the form of an extended resume, I came to discover the uniqueness of Streamlit as compared to typical front-end frameworks such as Angular and Bootstrap. Even though Streamlit is primarily used as a web application for dashboarding, its extensive features make it more aesthetically appealing to explore with as compared to alternatives such as Plotly and Shiny.

With the convenience of using Python as a beginner-friendly programming language, I have now decided to evolve this personal project into a time capsule - documenting key moments and achievements that I have attained since commencing my formal education at 7 years old. In addition, should I be successful in completing this project, I intend to provide my codes as open-source, so that other students can document their educational journey in a similar manner. My only request would be for other users to provide credit to this repository, especially if the end template is very similar to the end-product of this web application.

```python

import streamlit as st
import streamlit_option_menu import option_menu
from streamlit_lottie import_lottie
from PIL import image
import requests


image = Image.open("")
st.set_page_config(
    page_title = "My Web App Portfolio",
    layout = "wide",
    initial_sidebar_state = "expanded")


def load_lottieurl(url):
    r = requests.get(url)
    if r.status_code !=200:
        return None
    return r.json()


lottie_code = load_lottieurl("")
col1,col2 = st.columns([3,1])
with col1:
    st.write("##")
    st.subheader("Wecome to shizzy's app!")
    st.markdown("""_> "Data analysis is both art and science", ** Oluwaseun Emmanuel**""")
    st.write("[Read more] (github.com/seunBoyy)")
    st.write('---')

    with col2:
        st.header("C:\Users\user\Downloads\WhatsApp Image 2024-08-04 at 13.58.09_6856649a.jpg")
        st.image(image, use_column_width=True)

    st.write('---')

    with st.container():
        selected = option_menu(menu_title = "Main Menu", menu_options = ["About", "Projects", "Contact me"], icons = ["","",""], orientation = "horizontal")


if selected == "About":
    with st.container():
        col3,col4 = st.columns(2)
        with col3:
            st.write('')
            st.subheader("inquisitive, computer scientist passionate about turning data into insights")
            with col4:
                st_lottie("https://lottiefiles.com/free-animation/chart-diagram-hreI9ZgxO4")
                
                st.write('---')

    with st.container():
        col5,col6 = st.columns(2)
        with col5:
            st.subheader("Education
                         -Higher National Diploma (2020-2022)
                         -National Diploma (2016-2019)")
        st.write('---')

if selected == "Projects":
    with st.container():
        col7,col8 = st.columns(2)
        with col7:
               st.write("Here are some of the projects i've worked on: ")
               with col8:
                     st.image("C:\Users\user\Downloads\WhatsApp Image 2024-08-04 at 13.58.18_f799b065.jpg", caption = "project 1")
                     st.image("C:\Users\user\Downloads\WhatsApp Image 2024-08-04 at 13.58.19_c08fe846.jpg", caption = "project 2")
                     st.image("C:\Users\user\Downloads\WhatsApp Image 2024-08-04 at 13.58.20_2bfbda8c.jpg", caption = "project 3")
                     
        st.write('---')

if selected == "Contact Me":
    with st.container():
        col9,col10 = st.columns(2)
        with col9:
                st.title("Contact Me")
                with col10:
                     st_lottie(animation_contact, height = 200)
                     with st.form(key= "contact_form"):
                         name = st.text_input("Name")
                         email = st.text_input("Email")
                         message = st.text_area("Message")
                         submit_buttton = st.form_submit_button("send")
                         if submit_button:
                            st.success("Message sent!")
                            st.markdown("""
                                        <style>
                                        .contact = container {
                                            background-color: #f5f5f5;
                                            padding: 20px;
                                            border: 1px solid #ddd;
                                            border-radius: 10px
                                            box-shadow: 0px 0px 10px rgba(0,0,0,0.1);    }
                                        
                                        .contact-form {
                                            display: flex;
                                            flex-direction: column;
                                            align-items: center;    }
                                        
                                        .contact-form input, textarea{
                                            width: 100%,
                                            padding: 10px
                                            margin-bottom: 20px;
                                            border: 1px solid #ccc;
                                            border-radius: 5px; }
                                        
                                        .contact-form button [type= "submit"] {
                                            background-color: #4CAF50;
                                            color: #fff;
                                            paddind: 10px 20px;
                                            border: none;
                                            border-radius: 5px;
                                            cursor: pointer; }
                                        </style>
                                        """, unsafe_allow_html= True)

```
 
 #### Written in Python and Streamlit

