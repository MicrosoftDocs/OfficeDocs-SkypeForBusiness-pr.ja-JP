---
title: 予定表を使用して既存の電子メール システムにConnect Microsoft Teams Essentials (AAD ID) する
author: adjoseph
ms.author: adjoseph
ms.reviewer: jimmyw
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
searchScope:
- Microsoft Teams
search.appverid: MET150
description: Google ワークスペースなどの予定表を使用してMicrosoft Teams Essentials (AAD ID) を既存のメール システムに接続する方法について説明します
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 8bc388f533d39d6e1bc0140bcd975d6354898d5a
ms.sourcegitcommit: 296862e02b548f0212c9c70504e65b467d459cc3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/25/2022
ms.locfileid: "65674909"
---
# <a name="connect-microsoft-teams-essentials-aad-identity-to-an-existing-email-system-with-calendar"></a>予定表を使用して既存の電子メール システムにConnect Microsoft Teams Essentials (AAD ID) する

このガイドでは、Microsoft Teams Essentials (AAD Identity) を予定表を使用して既存の電子メール システムに接続するための構成手順について説明します。

Microsoft Teams Essentials (AAD Identity) は、会議、チャット、通話、コラボレーションとTeamsのベストを結び付けます。 Teams Essentials (AAD Identity) は、既存の電子メール システムに接続して、既存のメール 受信トレイ内のすべてのTeams通知、Teamsのすべての予定表イベント、既存のメール アドレスでTeamsにサインインする機能などの統合されたエクスペリエンスを提供できます。

接続すると、スケジュールされた会議や招待に対する応答を確認して、メールボックスとMicrosoft Teamsで共同作業を行うことができます。 また、Teamsや Google ワークスペースなどのサードパーティの会議ソフトウェアを使用して、予定表から受信した会議を表示および操作することもできます。

## <a name="prerequisites"></a>前提条件

この記事の構成手順には、Exchange Onlineからアイテムを自動的に転送するプロセスが含まれます。 既定では、スパム対策送信ポリシーによって自動転送は無効になっています。 このポリシーは、既存のメールボックスと予定表システムTeams Essentials に接続するために有効にする必要があります。

自動転送を有効にするには:

1. Microsoft 365 Defender ポータルに移動します。<https://security.microsoft.com/>
2. 左側のナビゲーション メニューの [ポリシー] セクション **の [電子メール & コラボレーション** > **ポリシー&ルール** > **脅威ポリシー** > **のスパム対策** ] に移動します。
3. [ **スパム対策ポリシー** ] ページで、一覧から **[スパム対策送信ポリシー (既定)]** を選択します。
4. 表示されるポリシーの詳細ポップアップで、[ **保護設定の編集]** を選択して自動転送ルールを変更します。
5. [ **転送ルール**] で、自動転送条件を **[オン - 転送] に** 変更し、変更を保存します。

:::image type="content" source="media/essentials-antispam.png" alt-text="Microsoft Defender Portal のスパム対策送信ポリシーポップアップを示す画像で、転送ルールの下で、転送が有効な状態です。" :::

送信スパム ポリシーの構成の詳細については、「送信スパム [フィルターの構成 - Office 365 |」を参照してください。Microsoft Docs](/microsoft-365/security/office-365-security/configure-the-outbound-spam-policy?view=o365-worldwide&preserve-view=true)。

## <a name="connect-teams-essentials-to-exchange-online-with-exchange-on-premises"></a>ExchangeオンプレミスでExchange OnlineするためのConnect Teams Essentials

オンプレミスでMicrosoft Teamsと Teams Exchange Onlineの間の接続を構成するハイブリッド アプローチを使用して、Essentials (AAD) が提供する必要があるすべてのExchangeを楽しむことができます。

オンプレミスメールボックスの予定表アクセスを機能させるには、「オンプレミスメールボックスの[Teams予定表 Exchangeアクセスを構成する - Microsoft Tech Community](https://techcommunity.microsoft.com/t5/exchange-team-blog/configuring-teams-calendar-access-for-exchange-on-premises/ba-p/1484009)

Exchangeオンプレミスのハイブリッド環境にMicrosoft Teams Roomsをデプロイするには、「オンプレミス[でExchange Microsoft Teams Roomsをデプロイする - Microsoft Teams |Microsoft Docs](rooms/with-exchange-on-premises.md)

## <a name="connect-teams-essentials-to-third-party-email-systems-with-calendar"></a>予定表を使用してサード パーティの電子メール システムに要点をConnect Teamsする

組織のメールボックスをMicrosoft 365に切り替える予定がない場合は、Teams Essentials を既存のサード パーティの電子メールおよび予定表システムに接続できます。 この接続を使用すると、既存のメール システムでTeams通知を受け取り、既存の会議の招待や予定表イベントをMicrosoft Teamsで表示できます。

### <a name="connect-teams-essentials-to-third-party-email-using-vanity-domain-google-workspace-example"></a>Connect Teams vanity ドメインを使用してサード パーティの電子メールに要点をConnect Teamsする (Google ワークスペースの例)

次のセクションでは、Google ワークスペースなどの予定表を使用してMicrosoft Teamsを既存のメール システムに接続する方法を示します。 この接続を実現するには、現在の電子メール システムをそのままにして、すべてのメールをExchange Onlineに転送し、予定表の種類のメールを除くすべてをフィルター処理します。 その際、予定表の種類のメールが削除されると、予定表のメールがTeams予定表に自動的に表示されます。

Microsoft 365で生成されたすべてのメールは Google ワークスペースに転送され、ユーザーはTeamsリマインダーと通知を受け取ります。 ユーザー ID (ユーザーのプライマリ 電子メールなど) を複製できます。 シングル サインオンも可能ですが、必須ではありません。 ユーザーは、サードパーティの予定表またはTeams予定表からTeams会議に参加できる必要があります。 別のTeams機能は期待どおりに機能します。

:::image type="content" source="media/essentials-googleworkspace.png" alt-text="EXO と Gmail の間のメール フローの図を示す画像":::

これらの例は、Exchange Online PowerShell [V2 モジュール](/powershell/exchange/exchange-online-powershell-v2&preserve-view=true)の一部である [Connect-ExchangeOnline](/powershell/module/exchange/connect-exchangeonline?view=exchange-ps&preserve-view=true) PowerShell コマンドレットに依存しています。 Connect-ExchangeOnline の実行時にエラーが発生した場合は、[EXO V2 モジュールのインストール](/powershell/exchange/exchange-online-powershell-v2?view=exchange-ps&preserve-view=true)を使用してモジュールをインストールするための推奨手順に従っていることを確認します。 Connect-ExchangeOnline資格情報の入力を求めるメッセージが表示されたら、必ずテナント管理者アカウントを使用してください。

#### <a name="step-one-set-up-a-new-microsoft-365-tenant-domain"></a>手順 1: 新しいMicrosoft 365 テナント ドメインを設定する

1. <https://admin.microsoft.com> で管理センターにアクセスします。

2. **[ドメイン** の **セットアップ** > ] に移動し、[**ドメインの追加]** を選択して既存のドメインを追加します。 ドメインを追加しない場合、組織内のユーザーは、自分の電子メール アドレスに onmicrosoft.com ドメインを使用します。 ユーザーを追加する前にドメインを追加してください。そのため、2 回設定する必要はありません。

3. TXT レコードを使用して確認するに関するページの手順に従って [、TXT レコードを使用してドメインを確認します](/microsoft-365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider?view=o365-worldwide&preserve-view=true)。

4. メッセージが表示されたら、[**Microsoft 365に DNS の構成を許可しない**] を選択します。

5. メッセージが表示されたら、既存の MX レコードは変更せずにそのままにしておきます。

6. 既存の SPF TXT レコードを更新して、Microsoft 365を含めます。

7. DKIM を手動で設定するには、次の手順に従って、Microsoft 365の DomainKeys 識別メール ([DKIM) を構成](/microsoft-365/security/office-365-security/use-dkim-to-validate-outbound-email?view=o365-worldwide&preserve-view=true)します。

8. Microsoft 365 管理センターに<https://admin.microsoft.com/AdminPortal/>サインインして DKIM を有効にする

9. 左側のナビゲーション パネルで、[**ドメインのセットアップ]** >  を選択 **します**。

10. チェック ボックスを使用して、現在のドメインの一覧から既存の Microsoft 以外のドメイン (例: TomislavK@thephone-company.com) を選択します。

11. **3 つの垂直ドット** を含むボタンを選択して、メニューを開きます。

12. メニューから [**既定として設定**] を選択します。

13. 既存のドメインを **既定として設定** するように表示されるウィンドウで、既定として設定されていることを確認します。
    :::image type="content" source="media/essentials-internalrelay2.png" alt-text="ドメインを既定として設定するための確認ダイアログの画像":::

    Microsoft 365にドメインを追加する方法の詳細については、「Microsoft 365[にドメインを追加する](https://support.office.com/article/add-a-domain-to-office-365-6383f56d-3d09-4dcb-9b41-b5f5a5efd611?ui=en-US&rs=en-US&ad=US)」で説明されている手順に従います。

#### <a name="step-two-add-users-and-assign-teams-essentials-licenses"></a>手順 2: ユーザーを追加し、Essentials ライセンスTeams割り当てる

1. 管理センター <https://admin.microsoft.com> に移動して、個々のユーザーを追加する

2. **[ユーザー** > **のアクティブなユーザー**] に移動し、[**ユーザーの追加]** を選択します。

3. [ **基本の設定]** ウィンドウで、基本的なユーザー情報を入力し、[ **次へ**] を選択します。
    - **名前：** 名と姓、表示名、ユーザー名を入力します。
    - **ドメイン：** ユーザーのアカウントのドメインを選択します。 たとえば、ユーザーのユーザー名が Jakob で、ドメインが contoso.com されている場合は、jakob@contoso.com を使用してサインインします。
    - **パスワード設定:** 自動生成されたパスワードを使用するか、ユーザーに対して独自の強力なパスワードを作成するかを選択します。  ユーザーが追加されたときに、電子メールでパスワードを送信するかどうかを決定します。

4. [ **製品ライセンスの割り当て** ] ウィンドウで、ユーザーの場所と適切なライセンスを選択します。 使用可能なライセンスがない場合でも、ユーザーを追加してライセンスを追加できます。 [次へ] を選択します。

5. このユーザーを管理者にする場合は、[ **オプション設定** ] ウィンドウで [ **ロール]** を展開します。 **[プロファイル情報]** を展開して、ユーザーに関する追加情報を追加します。

6. **[次へ**] を選択し、新しいユーザーの設定を確認し、必要に応じて他の変更を加えてから、[**追加の完了]** を選択して閉じます。

複数のユーザーを同時に追加するには、「[ユーザーの追加とライセンスの割り当て - Microsoft 365管理者|」の推奨手順に従います。Microsoft Docs](/microsoft-365/admin/add-users/add-users?view=o365-worldwide&preserve-view=true)

#### <a name="step-three-configure-google-workspace"></a>手順 3: Google ワークスペースを構成する

***添付ファイルをMicrosoft 365してストリップする電子メールの二重配信を構成します。***

1. Google の手順に従ってデュアル配信を設定します。 <https://support.google.com/a/answer/9228551?hl=en>

2. Office 365のルートを追加する

    - Google 管理 コンソールに<https://admin.google.com>移動します)
    - Gmail > ホスト> Google ワークスペース>アプリに移動します。
    - ルート名を入力します。 (たとえば、Microsoft 365)
    - [単一ホスト] を選択し、Microsoft 365のドメインに指定された MX レコードを入力します (例: ContosoLandscaping2-m365master-com.mail.protection.outlook.com)

    **オンプレミス/Exchange Onlineにメールが送信されたときに ATTR35 応答コード Exchangeを解決するスマート ホスト メソッド:**
    - [シングル ホスト] を選択し、テナントの初期ドメインの MX レコードをスマート ホストとして入力します。 初期ドメインは GUID.onmicrosoft.com 形式です。 GUID は、サービスへの登録の一環としてすべての組織に提供される一意の値です。 GUID は 128 ビット整数 (16 バイト) であり、一意の識別子が必要な場合はどこでもすべてのコンピューターとネットワークで使用できます。
    - コマンド ライン : nslookup -type MX GUID.onmicrosoft.com を使用して MX レコードを解決できます (例: contosolandscaping2.mail.protection.outlook.com)
    - **ポートの選択:25**
    - 推奨されるオプションを続行する

3. Office 365へのルートを構成する

    - **Google 管理 コンソール** を開きます。<https://admin.google.com>

    - **Apps** > **Google ワークスペース****の Gmail** > **ルーティング** に移動する > 

    - [**ルーティング**] タブで、[**構成**] を選択します。

    - ルール **の名前** を入力します。 (たとえば、Gmail から Office 365)

    - **電子メール メッセージに影響を与えるには**、[**受信]** と [**内部受信**] の両方を選択します。

    - **上記の種類のメッセージの場合は、[メッセージの** 変更] を選択 **します**。

    - [ **配信先]** で [ **受信者の追加]** を選択し、[追加] を選択 **してセカンダリ メール ルートを追加します。**

    - [ **受信者]** で下矢印 "" を選択し、[詳細設定] を選択 **します。**

    - [**ルートの変更**] を選択します。

    - 一覧から、前に作成したセカンダリ メール ルートを選択します

    - [**添付ファイル**] で、[**メッセージから添付ファイルを削除する**] を選択します。

    - 下にスクロールし、[ **保存]** を選択します。

***Microsoft 365からメールを受信するために、Google ワークスペースにサブドメインを追加します。***

  次に、サブドメインへのメールボックスMicrosoft 365転送ルールを作成します。 Microsoft 365からメールを受信するために Google ワークスペースで使用するサブドメインを選択します (g.contosolandscaping2.m365master.com など)

1. **Google 管理 コンソール** から開始する (admin.google.com)

2. **アカウント** > **ドメイン管理** > ドメインに移動 **する**

3. **[ドメインの追加] を選択する**

4. 選択したドメイン名を入力します

5. **ユーザー エイリアス ドメインを選択する**

6. [**ドメインの追加&確認を開始する**] を選択します

7. 確認が完了するまで待機し、ページを更新する

8. [**Gmail のアクティブ化]** を選択する

9. [**MX レコードのセットアップをスキップ** する] を選択し、[**次へ**] を選択します。

10. [**別のサーバーへのメールのルーティング**] ダイアログで、メールをルーティングするサーバーをメモして (たとえば、aspmx.l.google.com) 、[**別のメール サーバーを使用** する] を選択します。

***Microsoft 365からのメールがスパム フィルターをバイパスすることを許可する***

1. Google ワークスペース上のユーザーに電子メールを送信して、Microsoft 365 テナントから適切なヘッダーを見つけます。

2. メッセージを開き、[**元の表示**] を選択します。

3. Microsoft 365 テナントからのメールを一意に識別する電子メール ヘッダーを選択します。 (たとえば、X-MS-Exchange-CrossTenant-id: 92f60fc7-eab3-403b-9d7d-9d683bf0a4b5)

4. **Google 管理 コンソール** に移動します。<https://admin.google.com>

5. **Apps** > **Google ワークスペース****Gmail** > **コンプライアンス** に移動する > 

6. **コンテンツ コンプライアンス** に移動し、[**構成**] を選択します。

7. 設定に名前を付けます。 たとえば、Allowlist Microsoft 365電子メールです。

8. 受信チェック **に影響を与える電子メール メッセージ** の下

9. [**各メッセージで検索するコンテンツを記述する式を追加** する] で、**次のいずれかがメッセージと一致するかどうかを** 選択します。

10. **[式**] で 、[Xi の **追加**] を選択します。 [**追加] 設定** で、[**コンテンツの一致の詳細設定**] を選択します。

11. [**場所]** で [**完全なヘッダー**] を選択する

12. [**一致の種類]** で [**フル テキスト**] を選択します

13. コンテンツの下に、Microsoft 365 テナントからのメールを一意に識別する電子メール ヘッダーを入力します (たとえば、X-MS-Exchange-CrossTenant-id: 92f60fc7-eab3-403b-9d7d-9d683bf0a4b5)

14. **[保存] を選択する**

15. **[上記の式が一致する場合] で、[メッセージの変更] >次の** フィールドを実行し、[**スパム**] の **[このメッセージのスパム フィルターをバイパスする**] をオンにします。

16. **[保存] を選択する**

#### <a name="step-four-configure-microsoft-365-settings-for-the-integration"></a>手順 4: 統合のMicrosoft 365設定を構成する

*Microsoft 365から Gmail にメールをルーティングするようにコネクタを構成します。*

1. **Microsoft 管理 センター** に移動します。<https://admin.microsoft.com/AdminPortal>

2. 左側のナビゲーション メニューで [ **すべて表示** ] を選択します。

3. **[管理 センター**] **で [Exchange**] を選択し、新しいタブでExchange管理センターを開きます

4. **Exchange管理センター** の左側のナビゲーション メニューで、[**メール フロー** > **コネクタ**] を選択し、オーバーフロー メニュー (...) を開き、[コネクタの追加] を選択します。

5. [新しいコネクタ] ウィンドウの [**接続** 元] で、[**Office 365**] を選択します。

6. [**接続**] で組織のメール サーバーを選択し、[**次へ**] を選択します。

7. 新しいコネクタの **名前** (例: Gmail へ) を入力し、[**次へ**] を続行します。

8. [ **コネクタの使用** ] セクションで、 **メッセージをこのコネクタにリダイレクトするトランスポートルールが設定されている場合にのみ** 選択し、[ **次へ**] を選択します。

9. [ルーティング] セクションで、適切なスマート メール ホスト (aspmx.l.google.com など) を入力し、次 **へ** を選択 **+** して続行します。

10. [**セキュリティ制限**] セクションで、[**次へ**] を選択して既定の設定をそのまま使用します。

11. [**検証メール] セクション** で、Gmail システムの有効なメール アドレス (たとえば、johannal@g.contosolandscaping2.m365master.com) を入力し、**プラス記号 (+)** を選択して、[**検証**] を選択します。

12. 検証が完了するまで待機し、成功した場合は [次へ] を押します

13. [ **コネクタの確認**] で、構成が正しいことを確認し、[コネクタの作成] を押します。

14. コネクタが作成した通知が表示されたら、**完了** キーを押します。

*Microsoft 365メールボックスから Gmail にメールを転送します。*

1. **Microsoft 365 管理 センター** を使用して各メールボックスを更新するか、次のような **PowerShell** スクリプトを使用できます。

    ```powershell
    $forwardingDomain = "g.contosolandscaping2.m365master.com"
    Connect-ExchangeOnline
    $Mailboxes = Get-Mailbox -ResultSize Unlimited -Filter {RecipientTypeDetails -eq "UserMailbox"}
    Foreach ($mbx in $mailboxes) {

    Set-Mailbox $mbx.Identity -DeliverToMailboxAndForward $true -ForwardingSMTPAddress $($mbx.Alias,$forwardingDomain -join "@")
    }
    ```

    **Connect-ExchangeOnline のトラブルシューティング:**

    Connect-ExchangeOnline を実行しているときにエラーが発生していますか? これは、組織の自動メール転送ルールの結果である可能性があります。 既定では、自動転送は無効になっています。 Teams Essentials を Google ワークスペースに接続するには、ルールを有効にする必要があります。

    次のスクリプトを入力します。

   ```powershell
    Set-ExecutionPolicy Unrestricted
     ```

    その後、次のコマンドを実行します。

    ```powershell
    Enable-OrganizationCustomization
    Get-HostOutboundSpamFilterPolicy | set-HostedOutboundSpamFilterPolicy -AutoForwardingMode On
    ```

*予定表トランスポート ルールに直接Exchange Online構成します。*

1. この設定を構成すると、予定表の招待が自動的に受け入れられ、Teams予定表に表示されるため、ユーザーはOutlook Web Appで招待を操作する必要はありません。

2. 次のスクリプトを使用して、トランスポート ルールを作成できます。

    ```powershell
    Connect-ExchangeOnline
    New-TransportRule -Name "Direct to Calendar" -MessageTypeMatches Calendaring -SetHeaderName "X-MS-Exchange-Organization-CalendarBooking-Response" -SetHeaderValue Tentative
    New-TransportRule -Name "Direct to Calendar triage action" -MessageTypeMatches Calendaring -SetHeaderName "X-MS-Exchange-Organization-CalendarBooking-TriageAction" -SetHeaderValue MoveToDeletedItems

    ```

*メールボックスのOutlook on the webを無効にします。*

1. メールボックスの[Outlook on the webを無効にするには、「Exchange OnlineのメールボックスのOutlook on the webを有効または無効にする](/exchange/recipients-in-exchange-online/manage-user-mailboxes/enable-or-disable-outlook-web-app)」の手順に従います。

2. Exchange 管理 センターまたは **PowerShell** を使用して **、Outlook on the web** を無効にすることができます。 次の PowerShell の例を使用して、すべてのメールボックスのOutlook on the webを無効にすることができます。

    ```powershell
    Connect-ExchangeOnline
    $Mailboxes = Get-Mailbox -ResultSize Unlimited -Filter {RecipientTypeDetails -eq "UserMailbox"}
    Foreach ($mbx in $mailboxes) {
    Set-CASMailbox $mbx.Identity -OWAEnabled $false
    }
    ```

#### <a name="step-five-configure-exchange-online-domain-for-internal-relay"></a>手順 5: 内部リレーのExchange Online ドメインを構成する

この手順では、最終的な解決のために電子メールがサード パーティシステムに確実に送信されます。

1. **Microsoft 管理 センター** に移動します。<https://admin.microsoft.com/AdminPortal>

2. 左側のナビゲーションで、[**すべて表示**] を選択します

3. **[管理 センター**] **でExchange** を選択し、新しいタブで管理センター Exchange開きます

4. **管理センター Exchange** 左側のナビゲーション メニューから **[メール フロー**] を選択し、[**承認済みドメイン**] を選択します。

5. サード パーティシステムで構成されているドメイン名をタップします (たとえば、contosoLandscaping2.m365master.com)

    :::image type="content" source="media/essentials-internalrelay1.png" alt-text="メール フローのExchange管理センターの設定を示す画像。":::

6. **[内部リレー**] を選択し、[**保存**] をクリックします。

    :::image type="content" source="media/essentials-internalrelay2.png" alt-text="内部リレー設定を保存する動作を示す画像。":::

#### <a name="step-six-create-a-rule-to-delete-all-inbound-mail-to-exchange-online-except-for-calendaring"></a>手順 6: 予定表を除くすべての受信メールをExchange Onlineに削除するルールを作成する

1. このルールは **、Exchange 管理 センター** または **PowerShell** で構成できます。 次の **PowerShell** の例を使用してルールを作成できます。

    ```powershell
    Connect-ExchangeOnline
    New-TransportRule -Name "Delete all except Calendaring" -ExceptIfMessageTypeMatches Calendaring -FromScope NotInOrganization -DeleteMessage:$true
    ```

### <a name="connect-teams-essentials-to-third-party-email-not-using-vanity-domain-gmail-example"></a>Connect Teams Vanity ドメインを使用していないサード パーティの電子メールに関する要点 (Gmail の例)

Teams [G Suite アドオン](https://support.microsoft.com/office/install-the-teams-meeting-add-on-for-google-workspace-bba2dfbe-0b2b-4ee7-be10-261ad80ddb60)に主に依存してコンシューマー Gmail アカウントを Teams Essentials に接続することで、Google ワークスペースから直接Teams会議をスケジュールして参加できます。 これにより、画面共有、会議チャット、デジタルホワイトボードなどを使用してビデオ会議と電話会議をスケジュールできます。

Gmail を構成して、Exchange Onlineからメールをプルして、Microsoft 365で生成されたメールと Gmail に正常に到着Teams確認します。 この接続を実現するには、セキュリティの既定値を無効にする必要がある場合があります。これにより、強力な一意のパスワードを使用することが不可欠になります。 このシナリオではカスタム ドメインは必要ありませんが、使用する場合は Gmail で使用できるようにMicrosoft 365で構成できます。

:::image type="content" source="media/essentials-gmail.png" alt-text="Teams Essentials と Gmail の間のメール フローを示す画像":::

#### <a name="1-ensure-that-you-have-a-gmail-account-set-up"></a>1. Gmail アカウントが設定されていることを確認する

既に既存のアカウントを持っている場合は、次の手順に進むことができます。 そうでない場合は、 [新しい Google アカウントの作成](https://accounts.google.com/SignUp?hl=en) に関するページにアクセスして、新しい Gmail アカウントを設定します。

#### <a name="2-set-up-your-microsoft-365-tenant"></a>2. Microsoft 365 テナントを設定する

*AAD ユーザー Teams構成します。*

1. [「ユーザーの追加とライセンスの割り当て](/microsoft-365/admin/add-users/add-users?view=o365-worldwide&preserve-view=true)」のガイダンスに従って複数のユーザーを追加する

*ID 保護を構成します。*

1. アクティブな場合は、セキュリティの既定値を無効にします。

2. ユーザーの多要素認証を構成する

3. 条件付きアクセスを使用する場合は、メールボックスへの POP アクセスの例外を必ず行ってください

*Microsoft 365 管理 センターにドメインを追加します (省略可能)。*

1. ナビゲーションで [設定 > ドメイン] を選択し、[ドメインの追加] を選択します。

2. 適切なフィールドにドメイン名を入力します

3. 画面の指示に従って、TXT レコードでドメインを確認する

4. メッセージが表示されたら、Microsoft に DNS の構成を許可する

5. 手順を完了して、Microsoft 365への MX レコード ルートを確認します

6. Microsoft 365を含める SPF TXT レコードを構成する

7. Microsoft 365用に DKIM TXT レコードを構成する手順を完了します

8. ログアウトして管理 センターにサインインして DKIM が有効になっていることを確認する

#### <a name="3-configure-gmail"></a>3. Gmail を構成する

1. メールをシステムにプルExchange Online Gmail を構成する

2. Teams予定表アドインを構成する

3. Gmail でビジネス ドメインを使用できるようにする (省略可能)
