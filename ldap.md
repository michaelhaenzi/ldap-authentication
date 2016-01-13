LDAP Authentication
-------------------

###LDAP

LDAP (Lightweight Directory Access Protokoll) erlaubt es die Abfrage und Modifikation von Informationen eines
Verzeichnisdienstes (verteilte hierarchische Datenbank) über ein IP-Netzwerk.


###C# Syntax


```js
private bool Authenticate(string userName,
    string password, string domain)
{
    bool authentic = false;
    try
    {
        DirectoryEntry entry = new DirectoryEntry("LDAP://" + domain,
            userName, password);
        object nativeObject = entry.NativeObject;
        authentic = true;
    }
    catch (DirectoryServicesCOMException) { }
    return authentic;
}
```


###LDAP Attribute

Folgende Attribute können verwendet werden:
<br>[LDAP-Names](http://www.manageengine.com/products/ad-manager/help/csv-import-management/active-directory-ldap-attributes.html)
