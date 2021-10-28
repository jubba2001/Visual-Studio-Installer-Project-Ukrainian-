# Visual-Studio-Installer-Project-Ukrainian-
Ukrainian language support for Microsoft Visual Studio Installer Project (Visual Studio 2017, 2019)

Підтримка української мови для Microsoft Visual Studio Installer Project (Visual Studio 2017, 2019)

Для встановлення, потрібно:

1. Скопіювати папку 1058 до папки з діалогами Installer Project:
`{disk}:\Program Files (x86)\Microsoft Visual Studio\{version}\{edition}\Common7\IDE\CommonExtensions\Microsoft\VSI\bin\VsdDialogs`

2. В файлі проекту Visual Studio Installer Project (.vdproj) необхідно вказати код мови 1058 (Українська), та кодову сторінку 1251 (Кирилиця):

```"DeployProject"
{
  "LanguageId" = "3:1058"
  "CodePage" = "3:1251"
  "UILanguageId" = "3:1058"
  ...
}
```

3. Перезавантажити проект.

У вікні властивостей проекта буде написано `Localization` `Neutral`, але діалоги будуть завантажені українізовані, та мова msi-пакета буде Українська.

Якщо виникне потреба змінити переклад, це можливо зробити за допомогою програми Orca, яка входить до складу Windows SDK, який поставляється з VS 2019:
`{disk}:\Program Files (x86)\Windows Kits\10\bin\{version}\x86\Orca-x86_en-us.msi`

