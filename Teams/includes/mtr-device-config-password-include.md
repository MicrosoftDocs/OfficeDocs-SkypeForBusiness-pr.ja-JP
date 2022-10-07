
Microsoft 365 アカウントと同様に、新しく作成されたリソース アカウントのパスワードは、一定期間後に自動的に期限切れに設定されます。 ただし、リソース アカウントのパスワードの有効期限が切れた場合、サインインしたTeams Roomsデバイスは有効期限を再度サインインできません。 

リソース アカウントのパスワードをリセットしてから、各Teams Roomsデバイスに再度ログインする必要がないようにするには、アカウントのパスワードの有効期限を無効にできます。
  
> [!NOTE]
> **パスワードを期限切れにしない** 設定は、共有 Microsoft Teams デバイスの要件です。 ドメイン 規則で有効期限が切れていないパスワードを禁止している場合は、Teams デバイス リソース アカウントごとに例外を作成する必要があります。

次のいずれかのタブの手順に従って、パスワードの有効期限を無効にします。

#### <a name="azure-active-directory-20"></a>[**Azure Active Directory 2.0**](#tab/azure-active-directory2-password/)

最初に、Active Directory PowerShell に接続します。

```PowerShell
   Connect-AzureAD
```

次に、「 [パスワードを期限切れにならないように設定する」を](/microsoft-365/admin/add-users/set-password-to-never-expire#set-a-password-to-never-expire)参照してください。

次の使用例は、アカウント ConferenceRoom01@contoso.com のパスワードを無期限に設定します。

```PowerShell
Set-AzureADUser -ObjectID ConferenceRoom01@contoso.com -PasswordPolicies DisablePasswordExpiration
```

#### <a name="azure-active-directory-10"></a>[**Azure Active Directory 1.0**](#tab/azure-active-directory1-password/)

 1. MSOnline PowerShell に接続します。

       ```PowerShell
       Connect-MsolService
       ```

       Active Directory の詳細については、「 [Azure Active Directory (MSOnline)](/powershell/azure/active-directory/overview?view=azureadps-1.0&preserve-view=true)」を参照してください。

2. 次の構文を使用して、パスワードを期限切れにならないように設定します。

    ```PowerShell
    Set-MsolUser -Identity <samAccountName> -PasswordNeverExpires $true
    ```

    次の使用例は、アカウント ConferenceRoom01@contoso.com のパスワードを無期限に設定します。

    ```PowerShell
    Set-MsolUser -UserPrincipalName 'ConferenceRoom01@contoso.com' -PasswordNeverExpires $true
    ```

#### <a name="active-directory-on-premises"></a>[**Active Directory (オンプレミス)**](#tab/active-directory1-password/)

1. Active Directory PowerShell に接続します。

    ```PowerShell
       Import-Module ActiveDirectory
    ```
    
    Active Directory PowerShell の詳細については、「 [ActiveDirectory」を](/powershell/module/activedirectory)参照してください。

2. 次の構文を使用して、パスワードを期限切れにならないように設定します。

    ```PowerShell
    Set-ADUser -Identity <samAccountName> -PasswordNeverExpires $true
    ```

    次の使用例は、アカウント ConferenceRoom01@contoso.com のパスワードを無期限に設定します。

    ```PowerShell
    Set-ADUser -Identity ConferenceRoom01@contoso.com -PasswordNeverExpires $true
    ```

---