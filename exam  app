import streamlit as st

def main():
    st.set_page_config(page_title="Custom Exam Generator", layout="centered")
    st.title("📄 Custom Exam Generator")

    with st.form("exam_form"):
        st.subheader("School and Student Details")
        school_name = st.text_input("School Name")
        student_name = st.text_input("Student Name")
        admission_number = st.text_input("Admission Number")

        st.subheader("Exam Setup")
        title = st.text_input("Exam Title")
        instructions = st.text_area("Exam Instructions", value="Answer all questions.")
        num_questions = st.number_input("Number of Questions", min_value=1, max_value=100, value=5)

        questions = []
        for i in range(num_questions):
            q = st.text_input(f"Question {i+1}", key=f"q_{i}")
            questions.append(q)

        submitted = st.form_submit_button("Generate Exam")

        if submitted:
            if not school_name or not student_name or not admission_number:
                st.error("Please enter the school name, student name, and admission number.")
            elif not title:
                st.error("Please enter a title for the exam.")
            elif any(q.strip() == '' for q in questions):
                st.error("Please fill in all questions.")
            else:
                st.success("Exam Generated Successfully!")
                st.write(f"### {school_name}")
                st.write(f"### Exam Title: {title}")
                st.write(f"**Student Name:** {student_name}")
                st.write(f"**Admission Number:** {admission_number}")
                st.write(f"**Instructions:** {instructions}")
                for i, q in enumerate(questions):
                    st.write(f"**Q{i+1}:** {q}")

if __name__ == "__main__":
    main()
