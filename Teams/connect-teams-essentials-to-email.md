---
title: Connect Microsoft Teams付き既存AADシステムに Essentials (AAD ID) を追加する
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
description: Google Workspace のような予定表を使用Microsoft Teams Essentials (AAD Id) を既存のメール システムに接続する方法について説明します
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 6d113446971375ace51335a6654c8599f8d2c35b
ms.sourcegitcommit: be8b820caf4b5a1a91ad444ba93da1df20bf63ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/01/2021
ms.locfileid: "61257527"
---
# <a name="connect-microsoft-teams-essentials-aad-identity-to-an-existing-email-system-with-calendar"></a>Connect Microsoft Teams付き既存AADシステムに Essentials (AAD ID) を追加する

このガイドでは、Microsoft Teams Essentials (AAD Identity) を予定表を使用して既存のメール システムに接続するための構成手順について説明します。

Microsoft Teams (AAD ID) は、会議、チャット、通話、コラボレーションTeams最適な機能を提供します。 Teams Essentials (AAD Identity) は、既存のメール システムに接続して、すべての Teams 通知を既存のメール受信トレイに含め、Teams 内のすべての予定表イベント、既存のメール アドレスを使用して Teams にサインインする機能などの統合されたエクスペリエンスを提供できます。

接続すると、スケジュールされた会議に対する応答や、メールボックスと会議で共同作業を行う招待Microsoft Teams。 Google Workspace のようなサードパーティの会議ソフトウェアを使用して、Teamsから受信した会議を表示したり、操作したりすることもできます。

## <a name="prerequisites"></a>前提条件

この記事の構成手順には、アイテムを自動転送するプロセスが含Exchange Online。 既定では、自動転送はスパム対策送信ポリシーによって無効になります。 このポリシーは、Essentials を既存のメールボックスTeamsシステムに接続するために有効にする必要があります。

自動転送を有効にするには:

1. ポータル () Microsoft 365 Defenderに移動します。<https://security.microsoft.com/>
2. 左側のナビゲーション メニューで、[ポリシー] セクションの [&**グループ** ポリシー&脅威ポリシースパム対策]  >    >    >  に移動します。
3. [スパム対策 **ポリシー] ページで、** 一覧から [スパム対策送信ポリシー **(既定)** を選択します。
4. 表示されるポリシーの詳細フライアウトで、[保護設定の編集] を **選択** して、自動フォワードルールを変更します。
5. [ **転送ルール] で**、自動転送条件を **[オン- 転送が有効] に変更し** 、変更を保存します。

:::image type="content" source="media/essentials-antispam.png" alt-text="[転送ルール] で[オン]、転送が有効な状態の Microsoft Defender ポータルのスパム対策送信ポリシー フライアウトを示す画像。" :::

送信スパム ポリシーの構成の詳細については、「送信スパム フィルターの構成 - Office 365 | [Microsoft Docs](/microsoft-365/security/office-365-security/configure-the-outbound-spam-policy?view=o365-worldwide&preserve-view=true)。

## <a name="connect-teams-essentials-to-exchange-online-with-exchange-on-premises"></a>Connect Teams Essentials を使用Exchange OnlineオンプレミスExchangeを使用する

Teams Essentials (AAD) が提供する必要があるすべての機能を、ハイブリッドアプローチを使用して、Microsoft Teams と Exchange Online と Exchange オンプレミスの間の接続を構成することで利用できます。

オンプレミスのメールボックスで予定表へのアクセスを機能させるには[、「Exchange](https://techcommunity.microsoft.com/t5/exchange-team-blog/configuring-teams-calendar-access-for-exchange-on-premises/ba-p/1484009)オンプレミス メールボックスの Teams 予定表アクセスの構成 - Microsoft Tech Community

オンプレミスの Microsoft Teams を使用してハイブリッド環境に Exchange 会議室をデプロイするには、「Microsoft Teams Rooms with [Exchange on-premises - Microsoft Teams |Microsoft Docs](rooms/with-exchange-on-premises.md)

## <a name="connect-teams-essentials-to-third-party-email-systems-with-calendar"></a>Connect Teamsを使用して、Essentials をサード パーティのメール システムに追加する

組織のメールボックスを Microsoft 365 に切り替える予定はない場合は、Teams Essentials を既存のサード パーティのメールおよび予定表システムに接続できます。 この接続を使用すると、Teamsの会議出席招待と予定表イベントを表示しながら、既存のメール システムで通知を受信Microsoft Teams。

### <a name="connect-teams-essentials-to-third-party-email-using-vanity-domain-google-workspace-example"></a>Connect Teamsを使用して Essentials をサード パーティのメールに送信する (Google ワークスペースの例)

次のセクションでは、Google Workspace Microsoft Teamsを使用して既存のメール システムに接続する方法について説明します。 この接続を実現するには、現在のメール システムをそのままにし、すべてのメールを Exchange Online に転送し、予定表の種類のメールを除くすべてをフィルター処理します。 この場合、仮の種類のメールとカレンダー以外の種類のメールとして受け入Teamsカレンダーに予定表メールが自動的に表示されます。

Microsoft 365で生成されたメールはすべて Google Workspace に転送され、ユーザーは通知Teams通知を受け取ります。 ユーザー ID (ユーザーのプライマリ メールなど) を複製できます。 シングル サインオンも可能ですが、必須ではありません。 ユーザーは、サードパーティの予定表またはTeamsから会議に参加Teamsがあります。 別のTeams機能は期待通り動作します。

:::image type="content" source="media/essentials-googleworkspace.png" alt-text="EXO と Gmail の間のメール フローの図を示す画像":::

これらの例は、Connect Power [Exchange Online Shell V2](/powershell/exchange/exchange-online-powershell-v2&preserve-view=true)モジュールの一部である[Connect-ExchangeOnline](/powershell/module/exchange/connect-exchangeonline?view=exchange-ps&preserve-view=true) PowerShell コマンドレットに依存しています。 Connect-ExchangeOnline を実行するときにエラーが発生する場合は[、EXO V2](/powershell/exchange/exchange-online-powershell-v2?view=exchange-ps&preserve-view=true)モジュールをインストールする を使用してモジュールをインストールするための推奨される手順に従ってください。 資格情報Connect-ExchangeOnline求めるメッセージが表示されたら、必ずテナント管理者アカウントを使用してください。

**手順 1: 新しいテナント ドメインをMicrosoft 365する**

1. <https://admin.microsoft.com> で管理センターにアクセスします。

2. [ドメインの **セットアップ]**  >  **に移動し、[** ドメインの **追加] を選択** して既存のドメインを追加します。 ドメインを追加しない場合、組織内のユーザーは、メール アドレスに onmicrosoft.com ドメインを使用します。 ユーザーを追加する前に必ずドメインを追加してください。そのため、ユーザーを 2 回設定する必要はありません。

3. 「TXT レコードを使用して確認する」の手順に従って、TXT レコード [でドメインを確認します](/microsoft-365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider?view=o365-worldwide&preserve-view=true)。

4. メッセージが表示されたら **、[DNS を構成Microsoft 365許可しない] を選択します**。

5. メッセージが表示されたら、既存の MX レコードを変更せずにそのままにしてください。

6. 既存の SPF TXT レコードを更新して、既存の SPF TXT レコードMicrosoft 365。

7. 次の手順に従って、Microsoft 365用に DomainKeys Identified Mail [(DKIM) を構成し、DKIM を手動で設定します](/microsoft-365/security/office-365-security/use-dkim-to-validate-outbound-email?view=o365-worldwide&preserve-view=true)。

8. にサインインし、Microsoft 365 管理センターして <https://admin.microsoft.com/AdminPortal/> DKIM を有効にする

9. 左側のナビゲーション パネルで、[ドメインのセットアップ]  >  **を選択します。**

10. チェック ボックスを使用して、現在のドメインの一覧から既存の Microsoft 以外のドメイン (JohannaL@contosolandscapting2.m365master.com など) を選択します。

11. 3 つの垂直ドット **が付いたボタンを選び** 、メニューを開きます。

12. メニューから [既定に設定 **] を選択します。**

13. **既存のドメインを既定** に設定するために表示されるウィンドウで、既定として設定を確認します。
    :::image type="content" source="media/essentials-internalrelay2.png" alt-text="ドメインを既定として設定する確認ダイアログの画像":::

    ドメインを Microsoft 365 に追加する方法の詳細については、「ドメインをドメインに追加する」に記載[されている手順に](https://support.office.com/article/add-a-domain-to-office-365-6383f56d-3d09-4dcb-9b41-b5f5a5efd611?ui=en-US&rs=en-US&ad=US)Microsoft 365。

**手順 2: ユーザーを追加し、Essentials Teams割り当てる**

1. で管理センターに移動 <https://admin.microsoft.com> し、個々のユーザーを追加します。

2. [ユーザー] **[**  >  **アクティブなユーザー] に移動** し、[ユーザーの **追加] を選択します。**

3. [基本 **の設定] ウィンドウで、** 基本的なユーザー情報を入力し、[次へ] を **選択します**。
    - **名前:** 名と名、表示名、およびユーザー名を入力します。
    - **ドメイン:** ユーザーのアカウントのドメインを選択します。 たとえば、ユーザーのユーザー名が Jakob で、ドメインが contoso.com の場合は、ユーザー名を使用してサインイン jakob@contoso.com。
    - **パスワード設定:** 自動生成されたパスワードを使用するか、ユーザー用に独自の強力なパスワードを作成します。  ユーザーが追加された場合に、メールでパスワードを送信するかどうかを決定します。

4. [製品ライセンス **の割り当** て] ウィンドウで、ユーザーの場所と適切なライセンスを選択します。 使用可能なライセンスを持ってない場合でも、ユーザーを追加してライセンスを追加できます。 [次へ] を選択します。

5. [オプションの **設定]** ウィンドウで **、このユーザー** を管理者にする場合は、[ロール] を展開します。[ **プロファイル情報] を** 展開して、ユーザーに関する追加情報を追加します。

6. [ **次へ**] を選択し、新しいユーザーの設定を確認し、必要に応じてその他の変更を行い、[追加の完了] **を選択** して、閉じます。

複数のユーザーを同時に追加するには、「ユーザーの追加とライセンスの割り当て - 管理者アカウントの割り当て[」のMicrosoft 365手順|Microsoft Docs](/microsoft-365/admin/add-users/add-users?view=o365-worldwide&preserve-view=true)

**手順 3: Google ワークスペースを構成する**

***メールの二重配信を構成して、Microsoft 365を削除します。***

1. 二重配信を設定するには、Google の手順に従います。 <https://support.google.com/a/answer/9228551?hl=en>

2. ネットワークのルートを追加Office 365

    - Google 管理コンソール () に移動 <https://admin.google.com> します。
    - Google Workspace > Gmail > ホスト>します。
    - ルート名を入力します。 (例: Microsoft 365)
    - [Single host] を選択し、ドメインに指定した MX レコードを Microsoft 365します (例: ContosoLandscaping2-m365master-com.mail.protection.outlook.com)。

    **オンプレミス/オンプレミスにメールが送信された場合に ATTR35 応答コードを解決Exchangeスマート ホストメソッドExchange Online。**
    - [Single host] を選択し、スマート ホストとしてテナントの初期ドメインの MX レコードを入力します。 初期ドメインは、次の形式 GUID.onmicrosoft.com。 GUID は、サービスへの登録の一環としてすべての組織に提供される一意の値です。 GUID は 128 ビット整数 (16 バイト) であり、一意の識別子が必要な場合は、すべてのコンピューターとネットワークで使用できます。
    - コマンド ライン nslookup -type MX GUID.onmicrosoft.com を使用して MX レコードを解決できます (例: contosolandscaping2.mail.protection.outlook.com)
    - [ **ポート:25] を選択します。**
    - 推奨されるオプションに進む

3. ルートを構成してOffice 365

    - Google 管理 **コンソールを開** きます ( <https://admin.google.com>

    - [アプリ]  >  **Google ワークスペースの Gmail ルーティング**  >  **に移動**  >  **する**

    - [ルーティング] **タブで** 、[構成] を **選択します。**

    - ルールの **[名前]** を入力します。 (たとえば、Gmail を使用してOffice 365)

    - メール **メッセージに影響を与える場合** は、[受信] と [内部受信 **]**  **の両方を選択します。**

    - [ **上記の種類のメッセージの場合] で、[メッセージ** の変更 **] を選択します。**

    - [ **配信先] で 、[** 受信者の追加] **を選択** し、[追加] を **選択してセカンダリ メール ルートを追加します。**

    - [ **受信者] で**、下向き矢印 "" を選択し、[詳細設定] を **選択します。**

    - [ルート **の変更] を選択します。**

    - 一覧から、前に作成したセカンダリ メール ルートを選択します。

    - [添付 **ファイル] で**、[ **メッセージから添付ファイルを削除する] を選択します。**

    - 下にスクロールし、[保存] を **選択します**。

***Google ワークスペースにサブドメインを追加して、Microsoft 365 からメールを受信します。***

  次に、サブドメインへのメールボックスのMicrosoft 365ルールを作成します。 Google Workspace で使用するサブドメインを選択して、Microsoft 365からメールを受信する (g.contosolandscaping2.m365master.com など)

1. Google 管理 **コンソールから開始** する (admin.google.com)

2. [アカウント ドメイン **]**  >  **の [**  >  **ドメインの管理] に移動します。**

3. [ドメイン **の追加] を選択する**

4. 選択したドメイン名を入力する

5. ユーザー **エイリアス ドメインの選択**

6. [ **ドメインの追加] を&確認を開始する**

7. 確認が完了し、ページが更新されるのを待ちます

8. [Gmail の **ライセンス認証] を選択する**

9. [Mx **レコードのセットアップをスキップする] を選択** し、[次へ] を **選択します。**

10. [メール **を別** のサーバーにルーティングする] ダイアログで、メールのルーティング先のサーバーをメモし (aspmx.l.google.com など)、[別のメール サーバーを使用する] を **選択します。**

***スパム フィルターをバイパスMicrosoft 365からのメールを許可する***

1. Google ワークスペース上のユーザーにMicrosoft 365を送信して、テナントから適切なヘッダーを見つける。

2. メッセージを開き、[元のメッセージを表示 **] を選択します。**

3. テナントから送信されるメールを一意に識別するメール ヘッダー Microsoft 365します。 (例: X-MS-Exchange-CrossTenant-id: 92f60fc7-eab3-403b-9d7d-9d683bf0a4b5)

4. Google 管理 **コンソール () に移動** します。 <https://admin.google.com>

5. [アプリ **]**  >  **Google ワークスペースの Gmail**  >  コンプライアンス **に移動**  >  **する**

6. [コンテンツ コンプライアンス **] に移動し、[** 構成] を **選択します。**

7. 設定に名前を付けします。 たとえば、Allowlist は電子メールMicrosoft 365します。

8. [受信 **] チェック ボックスに影響を与える** メール メッセージの下

9. [ **各メッセージで検索するコンテンツを** 説明する式を追加する] で、次の条件がメッセージと一致 **する場合に選択します。**

10. [式 **] で**、[追加] **[xi] を** 選択します。 [設定 **の追加] で**、[高度なコンテンツ **の一致] を選択します。**

11. [場所 **] で [** 完全な **ヘッダー] を選択します。**

12. [一 **致の種類] で [** フル テキスト] **を選ぶ**

13. [コンテンツ] に、Microsoft 365 テナントからのメールを一意に識別するメール ヘッダーを入力します (例: X-MS-Exchange-CrossTenant-id: 92f60fc7-eab3-403b-9d7d-9d683bf0a4b5)。

14. [保存] **を選択する**

15. [ **上記の式が一致する** 場合] で、[メッセージの変更] > **のフィールドを** 実行し、[迷惑メール] の下のこのメッセージに対して [スパム フィルターを **バイパスする** ] チェック ボックスを **オンにしてください**。

16. [保存] **を選択する**

**手順 4: 統合Microsoft 365設定を構成する**

*メールを Gmail にルーティングMicrosoft 365コネクタを構成します。*

1. Microsoft 管理 **センター () に移動します** 。 <https://admin.microsoft.com/AdminPortal>

2. 左側の **ナビゲーション メニューで** [すべて表示] を選択します。

3. [**管理センター] で****、[Exchange]** を選択してExchangeタブで管理センターを開きます。

4. 管理センター **Exchange** 左側のナビゲーション メニューで、[メール フロー コネクタ]を選択し、オーバーフロー メニュー  >  (...) を開き、[コネクタの追加] を選択します。

5. 新 **しいコネクタ ウィンドウの**[接続から] で、[接続] **Office 365**

6. [ **接続] で組織** のメール サーバーを選択し、[次へ] を **選択します。**

7. 新しい **コネクタの名前** を入力し (例: Gmail へ)、[次へ] を続行 **します。**

8. [**コネクタの使用] セクション** で、[このコネクタにメッセージをリダイレクトするトランスポート ルールを設定している場合のみ] を選択し、[次へ] を選択 **します**。

9. [ルーティング] セクションで、適切なスマート メール ホスト (たとえば、aspmx.l.google.com) を入力し、[次へ] を **+** 続行 **します**。

10. [セキュリティ **制限] セクションで** 、[次へ] を選択して既定の設定を受け入 **れる**

11. [ **入力規則の電子** メール] セクションで、Gmail システムの有効なメール アドレス (johannal@g.contosolandscaping2.m365master.com など) を入力し、プラス記号 **(+)** を選択し、[検証] を選択 **します。**

12. 検証が完了し、成功した場合は [次へ] を押すのを待ちます。

13. [ **コネクタの確認] で**、構成が正しいか確認し、[コネクタの作成] を押します。

14. コネクタによって作成された通知が表示された場合は、Done キーを **押します。**

*メールを他のMicrosoft 365 Gmail に転送する*

1. Microsoft 365 管理 **センターを使用** して各メールボックスを更新するか、次のような **PowerShell** スクリプトを使用できます。

    ```powershell
    $forwardingDomain = "g.contosolandscaping2.m365master.com"
    Connect-ExchangeOnline
    $Mailboxes = Get-Mailbox -ResultSize Unlimited -Filter {RecipientTypeDetails -eq "UserMailbox"}
    Foreach ($mbx in $mailboxes) {
    
    Set-Mailbox $mbx.Identity -DeliverToMailboxAndForward $true -ForwardingSMTPAddress $($mbx.Alias,$forwardingDomain -join "@")
    } 
    ```

*予定表Exchange Onlineに直接アクセスするルールを構成する*

1. この設定を構成すると、ユーザーが Outlook Web App で招待を操作する必要なく、予定表の招待が Teams 予定表に表示され、自動的に受け入れOutlook Web App。

2. 次のスクリプトを使用して、トランスポート ルールを作成できます。

    ```powershell
    Connect-ExchangeOnline
    New-TransportRule -Name "Direct to Calendar" -MessageTypeMatches Calendaring -SetHeaderName "X-MS-Exchange-Organization-CalendarBooking-Response" -SetHeaderValue Tentative
    New-TransportRule -Name "Direct to Calendar triage action" -MessageTypeMatches Calendaring -SetHeaderName "X-MS-Exchange-Organization-CalendarBooking-TriageAction" -SetHeaderValue MoveToDeletedItems
    
    ```

*メールボックスOutlook on the webを無効にする*

1. 「メールボックスのメールボックスのOutlook on the webを無効にする」の[手順](/exchange/recipients-in-exchange-online/manage-user-mailboxes/enable-or-disable-outlook-web-app&preserve-view=true)にExchange Online、メールボックスのOutlook on the webを無効にします。

2. 管理センターまたは PowerShell Outlook on the webを使用 **Exchangeを****無効にできます**。 次の PowerShell の例を使用して、すべてのメールボックスのOutlook on the webを無効にできます。

    ```powershell
    Connect-ExchangeOnline
    $Mailboxes = Get-Mailbox -ResultSize Unlimited -Filter {RecipientTypeDetails -eq "UserMailbox"}
    Foreach ($mbx in $mailboxes) {
    Set-CASMailbox $mbx.Identity -OWAEnabled $false
    }
    ```

**手順 5: 内部リレー Exchange Onlineドメインを構成する**

この手順により、最終的な解決のためにメールがサード パーティシステムに送信されます。

1. Microsoft 管理 **センター () に移動します** 。 <https://admin.microsoft.com/AdminPortal>

2. 左側のナビゲーションで、[すべて表示] **を選択します。**

3. [**管理センター] で**、[Exchange]**を** Exchangeタブで管理センターを開きます。

4. 管理 **Exchange で、** 左側のナビゲーションメニューから [メール フロー] を選択し、[承諾されたドメイン **] を選択します。**

5. サードパーティ システムで構成されているドメイン名をタップします (例: contosoLandscaping2.m365master.com)

    :::image type="content" source="media/essentials-internalrelay1.png" alt-text="メール フロー Exchange管理センターの設定を示す画像。":::

6. [内部 **リレー] を選択** し、[保存] を **クリックします。**

    :::image type="content" source="media/essentials-internalrelay2.png" alt-text="内部リレー設定を保存する動作を示す画像。":::

**手順 6: 予定表を除くすべての受信メールを削除Exchange Onlineルールを作成する**

1. このルールは、管理センターまたは **PowerShell Exchangeで****構成できます**。 次の PowerShell の例 **を使用して** 、ルールを作成できます。

    ```powershell
    Connect-ExchangeOnline
    New-TransportRule -Name "Delete all except Calendaring" -ExceptIfMessageTypeMatches Calendaring -FromScope NotInOrganization -DeleteMessage:$true 
    
    ```

### <a name="connect-teams-essentials-to-third-party-email-not-using-vanity-domain-gmail-example"></a>Connect Teams使用していないサード パーティのメールに Essentials を追加する (Gmail の例)

コンシューマー Gmail アカウントを Teams Essentials に接続し、Teams G Suite アドオン に主に依存することで、Google Workspace から直接 Teams 会議をスケジュールして[参加できます](https://support.microsoft.com/en-us/office/install-the-teams-meeting-add-on-for-google-workspace-bba2dfbe-0b2b-4ee7-be10-261ad80ddb60)。 これにより、画面共有、会議チャット、デジタル ホワイトボードなどによるビデオ会議や電話会議をスケジュールできます。

Gmail からメールをプルして、Exchange Onlineで生成されたメールが Gmail に正常Microsoft 365受信Teamsを構成します。 この接続を実現するには、セキュリティの既定値を無効にする必要がある場合があります。これにより、強力な一意のパスワードを使用する必要があります。 このシナリオではカスタム ドメインは必要ありませんが、Gmail で使用する場合は、Microsoft 365 でカスタム ドメインを構成できます。

:::image type="content" source="media/essentials-gmail.png" alt-text="Essentials と Gmail の間のメール フロー Teams画像":::

**Gmail アカウントが設定されている必要があります。**

既存のアカウントを既に持っている場合は、次の手順に進みます。 設定されていない場合は、「 [新しい Google アカウントを作成する](https://accounts.google.com/SignUp?hl=en) 」にアクセスして、新しい Gmail アカウントを設定します。

**2. テナントをMicrosoft 365する**

*ユーザー Teams AAD構成する*

1. 「ユーザーの追加とライセンス[の割り当て」のガイダンスに従って](/microsoft-365/admin/add-users/add-users?view=o365-worldwide&preserve-view=true) 、複数のユーザーを追加する

*ID 保護を構成する*

1. アクティブな場合は、セキュリティの既定値を無効にします。

2. ユーザーの多要素認証を構成する

3. 条件付きアクセスを使用する場合は、メールボックスへの POP アクセスの例外を必ず設定してください

*ドメインを Microsoft 365 管理 センターに追加する (省略可能)*

1. ナビゲーションで [ドメイン] 設定 >選択し、[ドメインの追加] を選択します。

2. 適切なフィールドにドメイン名を入力します。

3. 画面上の指示に従って、TXT レコードを使用してドメインを確認します。

4. メッセージが表示されたら、Microsoft に DNS の構成を許可します。

5. MX レコードへのルートを確認する手順を完了Microsoft 365

6. SPF TXT レコードにデータを含Microsoft 365

7. DKIM TXT レコードを構成する手順を完了Microsoft 365

8. ログアウトして管理センターにもう一度サインインして、DKIM が有効になっているか確認する

**3. Gmail を構成する**

1. メールをシステムにプルExchange Online Gmail を構成する

2. 予定表アドインTeams構成する

3. Gmail でビジネス ドメインを使用する (省略可能)
