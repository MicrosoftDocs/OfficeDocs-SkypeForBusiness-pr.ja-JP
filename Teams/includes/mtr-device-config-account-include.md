
各Microsoft Teams Roomsデバイスには、独自のリソース アカウントが必要です。 リソース アカウントは、Teams Roomsデバイスがログインするアカウントであり、組織内のユーザーが Teams ルームを予約するために招待するアカウントです。

リソース メールボックスを作成するときに、定期的な会議を許可するか、ルームの自動招待を受け入れるか、今後招待を受け入れる日数などを指定できます。

> [!TIP]
> リソース アカウントに名前を付ける場合は、電子メール アドレスの先頭に標準の名前付け規則を使用することをお勧めします。 これは、Azure Active Directory での管理を容易にする動的グループの作成に役立ちます。 たとえば、Microsoft Teams Roomsに関連付けられるすべてのリソース アカウントに対して "mrt-" を使用できます。

> [!TIP]
> Exchange Onlineと Azure Active Directory を使用して、すべてのリソース アカウントを作成することをお勧めします。

次のいずれかのタブからメソッドを使用してリソース アカウントを作成します。

#### <a name="in-microsoft-365-admin-center"></a>[**Microsoft 365 管理センター**](#tab/m365-admin-center)

1. Microsoft 365 管理センターにサインインします。

2. Microsoft 365 テナントの管理者資格情報を指定します。

3. 左側のパネルの **[リソース** ] に移動し、[ **Rooms & equipment**] を選択します。 これらのオプションが左側のパネルで使用できない場合は、最初に **[すべて表示** ] を選択することが必要になる場合があります。

4. [ **リソースの追加]** を選択して、新しいリソース アカウントを作成します。 アカウントの表示名とメール アドレスを入力し、[保存] を選択 **します**。

5. 既定では、リソース アカウントは次の設定で構成されます。

    - 繰り返し会議を許可する
    - 次の制限外の会議を自動的に拒否する
      - 予約期間 (日): 180
      - 最大期間 (時間): 24
    - 会議出席依頼の自動承諾

    変更する場合は、[**閉じる**] を選択する前に [**予約オプションの編集**] を選択します。 後で変更する場合は、 **リソース** > **ルーム&機器** に移動し、リソース アカウントを選択します。 次に、[ **予約オプション**] で [編集] を選択 **します**。

6. **[ユーザー****アクティブ ユーザー**]  >  に移動し、作成したルームを選択してプロパティ パネルを開きます。

7. 次に、リソース アカウントにパスワードを割り当てます。 パネルで、[パスワードの **リセット**] を選択します。

8. 共有デバイスでユーザーにパスワードの変更を要求すると、サインインの問題が発生します。 [ **このユーザーが最初にサインインしたときにパスワードを変更するように要求** する] をオフにし、[ **パスワードのリセット**] を選択します。

また、帯域幅ポリシーまたは会議ポリシーをこのアカウントに適用する必要がある場合もあります。 後の手順でメールボックス ポリシーを設定できます。

#### <a name="with-exchange-online"></a>[**Exchange Onlineを使用する**](#tab/exchange-online)

1. [Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell) に接続します。

    ``` PowerShell
    Connect-ExchangeOnline
    ```

2. 既定では、会議室メールボックスにはアカウントが関連付けられていない。 Microsoft Teams で認証できるように、会議室メールボックスを作成するときにアカウントを追加します。

    新しいリソース メールボックスを作成している場合:

    ``` PowerShell
    New-Mailbox -MicrosoftOnlineServicesID <Office365 ID> -Name <String> -Alias <string> -Room -EnableRoomMailboxAccount $true  -RoomMailboxPassword (ConvertTo-SecureString -String '<Password>' -AsPlainText -Force)
    ```

    この例では、次の設定で新しい会議室メールボックスを作成します:

    - アカウント: ConferenceRoom01@contoso.com

    - 名前: ConferenceRoom01

    - エイリアス: ConferenceRoom01

    - アカウントのパスワード: P@ $ $W 0rd5959

    ``` PowerShell
    New-Mailbox -MicrosoftOnlineServicesID ConferenceRoom01@contoso.com -Name "ConferenceRoom01" -Alias ConferenceRoom01 -Room -EnableRoomMailboxAccount $true  -RoomMailboxPassword (ConvertTo-SecureString -String 'P@$$W0rd5959' -AsPlainText -Force)
    ```

Exchange ハイブリッド構成の場合は、オンプレミス ドメイン アカウントの電子メール アドレスを追加する必要があります。 詳細については、「[オンプレミスとOffice 365ユーザー アカウントディレクトリの同期](https://support.microsoft.com/topic/how-to-use-smtp-matching-to-match-on-premises-user-accounts-to-office-365-user-accounts-for-directory-synchronization-75673b94-e1b8-8a9e-c413-ee5a2a1a6a78)」を参照してください。

#### <a name="with-exchange-server"></a>[**Exchange Serverを使用する**](#tab/exchange-server)

  1. Exchange Management Shell に接続します。 [Exchange 管理シェルを開く](/powershell/exchange/exchange-server/open-the-exchange-management-shell) または、[リモート PowerShellを使用して Exchange サーバーに接続し ます](/powershell/exchange/exchange-server/connect-to-exchange-servers-using-remote-powershell)。

  2. 新しい会議室メールボックスを作成するには:

      ``` PowerShell
      New-Mailbox -UserPrincipalName <UPN> -Name <String> -Alias <String> -Room -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String '<Password>' -AsPlainText -Force)
      ```

      この例では、次の設定で新しい会議室メールボックスを作成します:

      - アカウント: ConferenceRoom01@contoso.com

      - 名前: ConferenceRoom01

      - エイリアス: ConferenceRoom01

      - アカウントのパスワード: P@ $ $W 0rd5959

   ``` PowerShell
   New-Mailbox -UserPrincipalName ConferenceRoom01@contoso.com -Name "ConferenceRoom01" -Alias ConferenceRoom01 -Room -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String 'P@$$W0rd5959' -AsPlainText -Force)
   ```

#### <a name="modify-an-existing-exchange-room-mailbox"></a>[**既存の Exchange 会議室メールボックスを変更する**](#tab/existing-account)

既存の会議室メールボックスを変更してリソース アカウントにするには、次の構文を使用します。

``` PowerShell
Set-Mailbox -Identity <RoomMailboxIdentity> -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String '<Password>' -AsPlainText -Force)
```

この例では、エイリアス値 ConferenceRoom02 を持つ既存の会議室メールボックスのアカウントを有効にし、パスワードを 9898P@$$W 0rd に設定します。

``` PowerShell
Set-Mailbox -Identity ConferenceRoom02 -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String '9898P@$$W0rd' -AsPlainText -Force)
```

Exchange ハイブリッド構成の場合は、オンプレミス ドメイン アカウントの電子メール アドレスも追加する必要があります。 詳細については、「[オンプレミスとOffice 365ユーザー アカウントディレクトリの同期](https://support.microsoft.com/topic/how-to-use-smtp-matching-to-match-on-premises-user-accounts-to-office-365-user-accounts-for-directory-synchronization-75673b94-e1b8-8a9e-c413-ee5a2a1a6a78)」を参照してください。

構文とパラメーターの詳細については、「[New-Mailbox](/powershell/module/exchange/mailboxes/new-mailbox)」と「[Set-Mailbox](/powershell/module/exchange/mailboxes/set-mailbox)」を参照してください。

> [!NOTE]
> Surface Hub で Teams Room 用にこのアカウントを作成する場合は、このアカウントで ActiveSync も有効にする必要があります。 これにより、Surface Hub から直接電子メールを送信できます。これにより、Whiteboard などの機能に使用できます。 詳細については、「 [ActiveSync ポリシーをデバイス アカウント (Surface Hub) に適用する」](/surface-hub/apply-activesync-policies-for-surface-hub-device-accounts) を参照してください。

---

> [!IMPORTANT]
> このリソース アカウントのみを使用してスペースを予約し、招待を自動的に承諾または拒否する場合は、設定が完了しました。 PSTN 通話にこのリソース アカウントを使用している場合は、 [Microsoft Teams アドオン ライセンス](../teams-add-on-licensing/microsoft-teams-add-on-licensing.md) に関するページを参照して、必要なライセンスを確認してください。
