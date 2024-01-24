class WebPage:
    def __init__(self, title="", header="", content="", footer=""):
        self.title = title
        self.header = header
        self.content = content
        self.footer = footer

    def __str__(self):
        return f"Title: {self.title}\nHeader: {self.header}\nContent: {self.content}\nFooter: {self.footer}"


class WebPageBuilder:
    def __init__(self):
        self.web_page = WebPage()

    def set_title(self, title):
        self.web_page.title = title
        return self

    def set_header(self, header):
        self.web_page.header = header
        return self

    def set_content(self, content):
        self.web_page.content = content
        return self

    def set_footer(self, footer):
        self.web_page.footer = footer
        return self

    def build(self):
        return self.web_page


class WebPageDirector:
    def create_article(self, content):
        builder = WebPageBuilder()
        builder.set_title("Article Page")
        builder.set_header("Article Header")
        builder.set_content(content)
        builder.set_footer("Article Footer")
        return builder.build()

    def create_form(self, title, fields):
        builder = WebPageBuilder()
        builder.set_title(title)
        builder.set_header("Form Header")
        builder.set_content(f"Form Fields: {fields}")
        builder.set_footer("Form Footer")
        return builder.build()


# Пример за използване на класовете:
director = WebPageDirector()

# Създаване на уеб страница със статично съдържание
article_page = director.create_article("This is the content of the article.")
print(article_page)

# Създаване на форма със специфични заглавие и полета
form_page = director.create_form("Registration Form", "Name, Email, Password")
print(form_page)
