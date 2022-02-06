---
title: SRS v1 管理 Web ポータルをサーバーに展開Skype for Business Server
ms.reviewer: null
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
  - NOCSH
ms.localizationpriority: medium
ms.assetid: 81822efa-2100-4017-a470-8a5b98c49522
ms.collection: M365-voice
description: Skype for Business Server Skype会議室システム v1 (SRS v1、以前は Lync Room System と呼ばれる) 管理 Web ポータルは、組織が会議室システムの会議室を維持するために使用Skype Web ポータルです。 管理者は、SRS v1 管理 Web ポータルを使用して、オーディオ/ビデオ デバイスの監視など、デバイスの正常性を監視できます。 このポータルを使用すると、管理者はリモートで診断情報を収集して会議室の正常性を監視できます。
---

# <a name="deploy-srs-v1-administrative-web-portal-in-skype-for-business-server"></a>SRS v1 管理 Web ポータルをサーバーに展開Skype for Business Server

Skype for Business Server Skype会議室システム v1 (SRS v1、以前は Lync Room System と呼ばれる) 管理 Web ポータルは、組織が会議室システムの会議室を維持するために使用Skype Web ポータルです。 管理者は、SRS v1 管理 Web ポータルを使用して、オーディオ/ビデオ デバイスの監視など、デバイスの正常性を監視できます。 このポータルを使用すると、管理者はリモートで診断情報を収集して会議室の正常性を監視できます。

この機能を使用するには、SRS v1 管理 Web ポータルをすべてのフロントエンド サーバー Skype for Business Serverする必要があります。 このガイドでは、SRS 管理 Web ポータルをインストールして構成する方法について管理者向け手順を説明します。 これは、管理者の管理に関する知識を持ち、Skype for Business Serverトポロジを変更する管理者権限を持つ管理者Skype for Business Server目的です。

SRS v1 管理 Web ポータルがサーバーに展開された後、管理者は自分のコンピューターまたはラップトップからサイトにログオンして、SRS v1 デバイスの状態を確認できます。

> [!IMPORTANT]
> [2015 Skype用の Microsoft Skype Room Systems v1 管理](https://www.microsoft.com/download/details.aspx?id=46906) Web ポータルをダウンロードSkype for Business Serverします。

このトピックの内容

- [SRS v1 管理 Web ポータルの環境を構成する](room-system-v1-administrative-web-portal.md#Config_Env)

- [SRS v1 管理 Web ポータルのインストール](room-system-v1-administrative-web-portal.md#Install_SRS)

- [SRS 管理 Web ポータルの使用](room-system-v1-administrative-web-portal.md#Use_Portal)

## <a name="configure-your-environment-for-the-srs-v1-administrative-web-portal"></a>SRS v1 管理 Web ポータルの環境を構成する
<a name="Config_Env"> </a>

SRS v1 管理 Web ポータルを使用するには、次の前提条件をインストールまたは構成する必要があります。

> [!IMPORTANT]
> サーバーが Kerberos 認証と NTLM 認証の両方で構成され、ドメインに参加していないコンピューターで SRS が実行されている場合、Kerberos 認証は失敗し、ユーザーは管理ポータルで SRS の状態を表示しません。 この問題を解決するには、NTLM 認証または NTLM 認証と TLS-DSK 認証 (Kerberos なし) の両方を使用してサーバーを構成するか、SRS コンピューターをドメインに参加します。

1. [Skype for Business Serverトポロジに累積的な更新プログラムSkype for Business Serverインストールします。

    更新プログラムを取得したり、更新プログラムに含まれているものについては、「[Update for Skype for Business Server 2015」を](https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015)参照してください。

2. SIP が有効な Active Directory ユーザーを作成します。

    SRS v1 管理 Web ポータルは、これらの資格情報を使用して、ユーザーからの情報を照会Skype for Business Server。 与えられた例のユーザー名は LRSApp です。

3. LRSSupportAdminGroup という名前の Active Directory セキュリティ グループを作成します。

    グループ スコープをグローバルとしてグループを作成し、セキュリティとしてグループの種類を作成します。 このグループに追加された SIP が有効なユーザーには、会議室の一覧を表示し、ログの収集などの特定のコマンドを実行する権限が与わります。

4. LRSFullAccessAdminGroup という名前の Active Directory セキュリティ グループを作成します。

    グループ スコープをグローバルとグループの種類としてグループを作成し、このグループに追加された Security.SIP が有効なユーザーは、1 つの Skype ルームですべての管理ポータル機能を使用する権限があります。 会議室の一括管理のサポートSkype手順 5 を参照してください。

     ![セキュリティ グループの役割を持つ管理者グループの一覧。](../../media/LRS_LRSFullAccessAdminGroup.png)

5. LRSPowerUserAdminsGroup という名前の Active Directory セキュリティ グループを作成します。

    グループ スコープをグローバルとしてグループを作成し、セキュリティとしてグループの種類を作成します。 このグループに追加された SIP が有効なユーザーは、会議室の一括管理を含むすべての管理ポータル機能Skype for Businessされます。

6. LRSSupportAdminGroup のメンバーとして LRSFullAccessAdminGroup を追加します。

     ![LRSSupportAdminGroup プロパティ メンバー ページ。](../../media/LRS_Add_LRSSupportAdminGroup.png)

7. LRSSupport という名前の SIP が有効な Active Directory ユーザーを作成します。 このユーザーを LRSSupportAdminGroup に追加します。

     ![LRSSupportAdminGroup プロパティ メンバー ページ。](../../media/LRS_Add_LRS_SIP_SupportUser.png)

8. [2010 SP1 ASP.NET Visual Web Developer 2010 SP1 Visual Studio MVC 4 をインストールします](https://go.microsoft.com/fwlink/p/?LinkId=323967)。

## <a name="install-the-srs-v1-administrative-web-portal"></a>SRS v1 管理 Web ポータルのインストール
<a name="Install_SRS"> </a>

[2015 Skype用の Microsoft Skype Room Systems v1 管理](https://www.microsoft.com/download/details.aspx?id=46906) Web ポータルをダウンロードSkype for Business Serverします。

SRS v1 管理 Web ポータルをインストールするには、次の手順を実行します。

1. 管理シェルで次のコマンドレットを実行して、信頼Skype for Business Server構成します。

   ```powershell
   Set-CsWebServer -Identity POOLFQDN -MeetingRoomAdminPortalInternalListeningPort 4456 -MeetingRoomAdminPortalExternalListeningPort 4457
   ```

2. ポータルをインストールするには **ミーティング ルームをダウンロード** MeetingRoomPortalInstaller.msi管理者として実行します。

3. 次の場所Web.configファイルを開きます。

    %Program Files%\Skype for Business Server 2015\Web Components\ミーティング ルーム\Int\Handler\

4. Web.Config ファイルで、PortalUserName を「[SRS v1 管理 Web](room-system-v1-administrative-web-portal.md#Config_Env) ポータルの環境を構成する」セクションの手順 2 で作成したユーザー名に変更します (手順の推奨名は LRSApp です)。

    ```xml
    <add key="PortalUserName" value="sip:LRSApp@domain.com" />
    ```

5. SRS v1 管理ポータルは信頼できるアプリケーションなので、ポータル構成でパスワードを指定する必要はありません。 このユーザーがローカル レジストラーとは異なるレジストラーを使用している場合は、レジストリ ファイルに次の行を追加してレジストラーを指定Web.Configがあります。

   ```xml
   <add key="PortalUserRegistrarFQDN" value="pool-xxxx.domain.com" />
   ```

6. 使用するポートが 5061 以外の場合は、次の行を次の行Web.Configします。

   ```xml
   <add key="PortalUserRegistrarPort" value="5061" />
   ```

### <a name="verify-installation-of-the-srs-administrative-web-portal"></a>SRS 管理 Web ポータルのインストールを確認する

SRS v1 管理 Web ポータルのインストールを確認するには、次の手順を実行します。

1. フロントエンド サーバーで、次の URL を参照します。

    \<fe-server\>https:///lrs

    次の図に示すように、エラーは表示されません。

     ![Lync Room System Admin Portal サインイン画面。](../../media/LRS_AdminPortalSignIn.png)

2. エラーが表示されない場合は、トポロジ内の他のコンピューターから次の URL にアクセスしてみてください。

    \<fe-server\>https:///lrs

    ページにアクセスするには、「自動クライアント サインインに必要な DNS レコード」の説明に従って [DNS レコードを追加する必要があります](/previous-versions/office/communications-server/bb663700(v=office.12))。

## <a name="use-the-srs-administrative-web-portal"></a>SRS 管理 Web ポータルの使用
<a name="Use_Portal"> </a>

サーバーに SRS を展開した後、ブラウザーから SRS v1 管理 Web ポータルにサインインすることで、すべての SRS ルームの状態を確認できます。

### <a name="sign-in"></a>サインイン

1. 次の URL を参照します。

    \<fe-server\>https:///lrs

2. LRSSupport アカウントの資格情報、または LRSSupportAdminGroup セキュリティ グループに追加されたアカウントを入力します。

![Lync Room System Admin Portal サインイン画面。](../../media/LRS_AdminPortalSignIn.png)

### <a name="srs-administrative-web-portal-summary-page"></a>SRS 管理 Web ポータルの概要ページ

概要ページには、サーバーに展開されているすべての SRS ルームに関する次の情報が表示されます。

- **タグ** 管理者がルームに与えるカスタム名。 タグは、ルーム名をクリックしてポータルで設定できます。

- **正常性**[ルームの正常性] ページの [正常性] セクションに表示される、部屋の正常性の集計状態から派生した、部屋の正常性設定します。

- **次の会議** 次の会議がスケジュールされる日時。

- **SRS バージョン、製造元、モデル** これらの値は SRS で事前設定されています。 製造元によっては、これらのフィールドは空白のままになる場合があります。

- **最後の更新** Web ページが最後に更新された時刻を表示します。

![Lync Room System Admin Portal Summary View。](../../media/LRS_AdminPortal_Summary_view.png)

> [!NOTE]
> LRSPowerUserAdminsGroup セキュリティ グループの一部である場合にのみ、[一括管理] メニューが表示されます。

### <a name="srs-room-information"></a>SRS ルーム情報

ポータルの [会議室情報] セクションでは、個々の SRS ルームを表示および構成できます。 このセクションには、設定、ログ、正常性の 4 つのセクションがあります。

#### <a name="settings"></a>Settings

[設定] セクションでは、ルームのパスワード、ルーム タグ、および既定のボリューム レベルを設定できます。 これらの設定を構成した場合、変更は SRS コンソールを再起動した後にのみレプリケートされます。 リリース 15.12 以降を使用している SRS デバイスのシステム更新プログラムの設定だけが表示されます。

![Lync Room System Admin Portal Room 設定。](../../media/LRS_AdminPortal_RoomInfoSettings.png)

#### <a name="details"></a>詳細

[詳細] セクションには、SRS ルームの設定の読み取り専用の概要 (最後の更新時刻など) が表示されます。次の会議。最後の更新、メンテナンス、調整。既定のスピーカー、マイク、および呼び出し音の設定。バージョン。SIP URI。各画面に関する画面と詳細の数。状態、およびアクティビティを指定します。

![Lync Room System Admin Portal 詳細ビュー。](../../media/LRS_AdminPortal_Detail_view.png)

#### <a name="troubleshooting"></a>トラブルシューティング

[トラブルシューティング] セクションを使用して、ログをリモートで収集し、指定した場所に保存できます。 SRS コンソール (SRS ユーザー インターフェイス) を再起動するか、システム全体を再起動することもできます。 ログを収集するには、指定した形式のフォルダー パスを指定し、フォルダーに SRS コンピューター アカウントに対する書き込みアクセス許可が付与されている必要があります。 ログ サイズが大きすぎる場合、ログの収集が完了するには最大 5 分かかる場合があります。 ページを更新すると、最新の状態が表示されます。

#### <a name="health"></a>正常性

[正常性] セクションでは、Skype for Business Server接続、オーディオ デバイス、ビデオ デバイス、復元状態、および画面デバイスの正常性を視覚的に示します。

![Lync Room System Admin Portal Room Health.](../../media/LRS_AdminPortal_RoomInfoHealth.png)

### <a name="additional-notes-about-the-administrative-web-portal"></a>管理 Web ポータルに関するその他の注意事項

> [!NOTE]
>  設定の変更は、SRS システムが再起動された後にのみ適用されます。> LRSApp アカウントのパスワードの有効期限が切れると、会議室の状態を確認できません。 LRSAppuser アカウント のパスワードが期限切れになることはありませんか、有効期限が近い場合は必ずパスワードを更新してください。> SRS 管理 Web ポータルは、オンプレミス展開でのみサポートされます。

### <a name="bulk-management"></a>一括管理

SRS ルームの一括管理は、高度な IT 管理者向けに設計された機能で、ワークフローを簡素化し、時間を節約できる便利なツールを使用して、複数のルームを一括でリモートで管理できます。

この機能を確認するには、ユーザーを特別なセキュリティ グループ **LRSPowerUserAdminsGroup のメンバーとしてプロビジョニングする必要があります**。

一括管理で選択できる SRS ルームの数に制限はありません。 ただし、一度に実行できる一括管理操作は 1 つのみです。

一括管理操作を実行するには、監視する会議室を選択し、[一括管理] メニューをクリックします。

### <a name="frequently-asked-questions"></a>よく寄せられる質問

#### <a name="why-cant-i-sign-in-to-the-administrative-web-portal"></a>管理 Web ポータルにサインインできない理由

開いていると https://localhost/lrs、サインイン ページが表示されますが、資格情報を入力するとサインインできません。 この場合は、管理 Web ポータル https://FQDNofFEserver/SRS にサインインするために開く必要があります。

#### <a name="why-cant-i-see-srs-v1-in-the-administrative-web-portal"></a>管理 Web ポータルに SRS v1 が表示できない理由

- 展開に SRS アカウントが含み、SRS 管理 Web ポータルの展開の推奨事項に従って作成される必要があります。 SRS アカウントが、Enable-CsUser ではなく Enable-CsMeetingRoom を使用してプロビジョニングSkype for Business Server。

- SRS アカウントを作成し、管理 Web ポータルでアカウントを表示できない場合は、**meetingPortal** コンポーネントを選択した Skype for Business Server ログ ツールを使用してサーバー ログを収集し、SRS サポート連絡先に送信します。

- SRS アカウントを作成し、管理 Web ポータルでアカウントを表示できない場合は、Fiddler を使用してクライアント ログを収集し、ブラウザー開発ツールからコンソール ログをコピーしてから、SRS サポート連絡先に送信します。 また、詳細なログを取得するために、Web.configのトレース レベルの値を変更できます。

  ```xml
  <system.diagnostics>
    <switches>
      <!--
      This switch controls logging message levels. 0 implies
      logging is turned off. 1 implies only errors are logged,
      2 implies errors &amp; warnings. 4 is the most detailed.
      -->
      <add name="TraceLevelSwitch" value="3" />
    </switches>
  </system.diagnostics>
  ```

#### <a name="why-cant-i-see-the-status-of-srs-in-the-administrative-web-portal"></a>管理 Web ポータルで SRS の状態が表示できない理由

- LRSApp ユーザー アカウントが SIP が有効になっているか確認します。

- 問題が解決し続ける場合は、D:\Trace\LRSAdminLogs\, から SRS システムの **Trace.log** ファイルを収集し、SRS サポート連絡先に送信します。

#### <a name="why-cant-i-see-the-bulk-management-menus-for-srs-in-the-administrative-web-portal"></a>管理 Web ポータルに SRS の一括管理メニューが表示できない理由

LRSApp ユーザー アカウントが SIP が有効であり、LRSPowerUserAdminsGroup セキュリティ グループの一部である必要があります。

#### <a name="does-the-srs-v1-administrative-web-portal-work-with-microsoft-teams-rooms"></a>SRS v1 管理 Web ポータルは、会議室とMicrosoft Teamsしますか?

いいえ。