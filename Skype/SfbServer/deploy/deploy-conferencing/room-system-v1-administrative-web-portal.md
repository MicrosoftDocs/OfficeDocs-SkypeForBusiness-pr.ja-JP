---
title: Skype for Business Server での SRS v1 管理 Web ポータルの展開
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 81822efa-2100-4017-a470-8a5b98c49522
ms.collection: M365-voice
description: Skype for Business Server Skype Room Systems v1 (旧称 Lync Room System) 管理 Web ポータルは、組織が Skype Room Systems の会議室を維持するために使用できる web ポータルです。 管理者は、SRS v1 管理 Web ポータルを使用して、デバイスの正常性を監視できます (オーディオ/ビデオデバイスの監視など)。 このポータルを使用すると、管理者はリモートで診断情報を収集して、会議室の状態を監視できます。
ms.openlocfilehash: d718adb60437fdd7e08724a5ba5fc48fa120425e
ms.sourcegitcommit: 693205da865111380b55c514955ac264031eb2fd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/02/2020
ms.locfileid: "42045900"
---
# <a name="deploy-srs-v1-administrative-web-portal-in-skype-for-business-server"></a>Skype for Business Server での SRS v1 管理 Web ポータルの展開

Skype for Business Server Skype Room Systems v1 (旧称 Lync Room System) 管理 Web ポータルは、組織が Skype Room Systems の会議室を維持するために使用できる web ポータルです。 管理者は、SRS v1 管理 Web ポータルを使用して、デバイスの正常性を監視できます (オーディオ/ビデオデバイスの監視など)。 このポータルを使用すると、管理者はリモートで診断情報を収集して、会議室の状態を監視できます。

この機能を使用するには、すべての Skype for Business Server フロントエンドサーバーに SRS v1 管理 Web ポータルを展開する必要があります。 このガイドでは、管理者が SRS 管理 Web ポータルをインストールおよび構成する方法について説明します。 Skype for business Server の管理について理解している管理者と、Skype for Business Server のトポロジを変更するための管理者ユーザー権限を持つ管理者を対象としています。

SRS v1 管理 Web ポータルがサーバーに展開されると、管理者は、自分のコンピューターまたはラップトップからサイトにログオンすることによって、ステータス SRS v1 デバイスを確認できます。

> [!IMPORTANT]
> Skype for business [Server 2015 の Microsoft Skype Room Systems V1 管理 Web ポータルを](https://www.microsoft.com/download/details.aspx?id=46906)ダウンロードします。

このトピックの内容

- [SRS v1 管理 Web ポータルの環境を構成する](room-system-v1-administrative-web-portal.md#Config_Env)

- [SRS v1 管理 Web ポータルをインストールする](room-system-v1-administrative-web-portal.md#Install_SRS)

- [SRS 管理 Web ポータルを使用する](room-system-v1-administrative-web-portal.md#Use_Portal)

## <a name="configure-your-environment-for-the-srs-v1-administrative-web-portal"></a>SRS v1 管理 Web ポータルの環境を構成する
<a name="Config_Env"> </a>

SRS v1 管理 Web ポータルを使用するには、次の前提条件をインストールまたは構成する必要があります。

> [!IMPORTANT]
> サーバーが Kerberos 認証と NTLM 認証の両方を使用して構成されていて、ドメインに参加していないコンピューター上で SRS が実行されている場合、Kerberos 認証が失敗し、ユーザーには管理ポータルの SRS の状態が表示されません。 この問題を解決するには、サーバーを NTLM 認証または NTLM と DSK 認証 (Kerberos を使用しない) の両方で構成するか、または SRS コンピューターをドメインに参加させます。

1. Skype for business Server トポロジで Skype for Business Server の累積的な更新プログラムをインストールします。

    更新プログラムを入手するには、「 [Skype For Business Server 2015 の](https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015)更新プログラム」を参照してください。

2. SIP 対応の Active Directory ユーザーを作成します。

    SRS v1 管理 Web ポータルは、これらの資格情報を使用して Skype for Business Server から情報を照会します。 指定された例のユーザー名は LRSApp です。

3. LRSSupportAdminGroup という名前の Active Directory セキュリティグループを作成します。

    グループスコープを持つグループを [グローバル] および [グループの種類] としてセキュリティとして作成します。 このグループに追加される SIP 対応ユーザーは、ルームのリストを確認し、ログの収集などの特定のコマンドを実行することを承認されます。

4. LRSFullAccessAdminGroup という名前の Active Directory セキュリティグループを作成します。

    グループスコープを持つグループを [グローバル] および [グループの種類] として [セキュリティ] として作成します。このグループに追加される SIP 対応ユーザーは、1つの Skype 会議室ですべての管理ポータル機能を使用することを承認されています。 Skype ルームの一括管理のサポートを含めるには、手順5を参照してください。

     ![セキュリティグループの役割を持つ管理グループの一覧](../../media/LRS_LRSFullAccessAdminGroup.png)

5. LRSPowerUserAdminsGroup という名前の Active Directory セキュリティグループを作成します。

    グループスコープを持つグループを [グローバル] および [グループの種類] としてセキュリティとして作成します。 このグループに追加された SIP 対応ユーザーは、Skype for Business ルームの一括管理を含む、すべての管理ポータル機能を使用することを承認されています。

6. LRSFullAccessAdminGroup を LRSSupportAdminGroup のメンバーとして追加します。

     ![LRSSupportAdminGroup Properties メンバーページ](../../media/LRS_Add_LRSSupportAdminGroup.png)

7. LRSSupport という名前の SIP 対応 Active Directory ユーザーを作成します。 このユーザーを LRSSupportAdminGroup に追加します。

     ![LRSSupportAdminGroup Properties メンバーページ](../../media/LRS_Add_LRS_SIP_SupportUser.png)

8. [ASP.NET MVC 4 For Visual Studio 2010 sp1 および Visual Web Developer 2010 SP1](https://go.microsoft.com/fwlink/p/?LinkId=323967)をインストールします。

## <a name="install-the-srs-v1-administrative-web-portal"></a>SRS v1 管理 Web ポータルをインストールする
<a name="Install_SRS"> </a>

Skype for business [Server 2015 の Microsoft Skype Room Systems V1 管理 Web ポータルを](https://www.microsoft.com/download/details.aspx?id=46906)ダウンロードします。

SRS v1 管理 Web ポータルをインストールするには、次の手順を実行します。

1. Skype for Business Server 管理シェルで次のコマンドレットを実行して、信頼されたアプリケーションポートを構成します。

   ```powershell
   Set-CsWebServer -Identity POOLFQDN -MeetingRoomAdminPortalInternalListeningPort 4456 -MeetingRoomAdminPortalExternalListeningPort 4457
   ```

2. 会議室ポータルをインストールするには、 **MeetingRoomPortalInstaller**をダウンロードして、管理者として実行します。

3. Web.config ファイルを次の場所から開きます。

    % Program Files%\Skype for Business Server 2015 (Web Components\Meeting Room Portal\Int\Handler\

4. Web.config ファイルで、PortalUserName を次の手順2で作成したユーザー名に変更します。セクション「[SRS V1 管理 Web ポータルの環境を構成する](room-system-v1-administrative-web-portal.md#Config_Env)」 (手順は LRSApp の推奨名)。

    ```xml
    <add key="PortalUserName" value="sip:LRSApp@domain.com" />
    ```

5. SRS v1 管理ポータルは信頼されたアプリケーションなので、portal 構成でパスワードを指定する必要はありません。 このユーザーがローカルレジストラーとは別のレジストラーを使用している場合は、Web.config ファイルに次の行を追加して、レジストラーを指定する必要があります。

   ```xml
   <add key="PortalUserRegistrarFQDN" value="pool-xxxx.domain.com" />
   ```

6. 使用しているポートが5061以外の場合は、web.config ファイルに次の行を追加します。

   ```xml
   <add key="PortalUserRegistrarPort" value="5061" />
   ```

### <a name="verify-installation-of-the-srs-administrative-web-portal"></a>SRS 管理 Web ポータルのインストールを確認する

SRS v1 管理 Web ポータルのインストールを確認するには、次の手順を実行します。

1. フロントエンドサーバーで、次の URL を参照します。

    https:// \<fe-server\> /lrs

    次の図に示すように、エラーは表示されません。

     ![Lync Room System 管理者ポータルのサインイン画面](../../media/LRS_AdminPortalSignIn.png)

2. エラーが表示されない場合は、トポロジ内の他のコンピュータから次の URL にアクセスしてみてください。

    https:// \<fe-server\> /lrs

    ページにアクセスするには、「[自動クライアントサインインに必要な Dns レコード](https://go.microsoft.com/fwlink/p/?LinkId=318056)」の説明に従って、dns レコードを追加する必要があります。

## <a name="use-the-srs-administrative-web-portal"></a>SRS 管理 Web ポータルを使用する
<a name="Use_Portal"> </a>

サーバーに SRS を展開した後、ブラウザーから SRS v1 管理 Web ポータルにサインインして、すべての SRS ルームの状態を確認できます。

### <a name="sign-in"></a>サインイン

1. 次の URL を参照します。

    https:// \<fe-server\> /lrs

2. LRSSupport アカウントの資格情報、または LRSSupportAdminGroup セキュリティグループに追加されたアカウントを入力します。

![Lync Room System 管理者ポータルのサインイン画面](../../media/LRS_AdminPortalSignIn.png)

### <a name="srs-administrative-web-portal-summary-page"></a>SRS 管理 Web ポータルの概要ページ

概要ページには、サーバーに展開されているすべての SRS ルームに関する次の情報が表示されます。

- **タグ**管理者がルームに付与するカスタム名。 タグは、ルーム名をクリックすることで、ポータルで設定できます。

- **正常性**ルームの正常性の状態。会議室の設定ページの [正常性] セクションに表示されている、会議室の状態の総計から導出されます。

- **次の会議**次の会議がスケジュールされた日時。

- **SRS のバージョン、製造元、モデル**これらの値は、SRS で事前設定されています。 製造元によっては、これらのフィールドが空白のままになっている場合があります。

- **最終更新**Web ページが最後に更新された日時を表示します。

![Lync Room System 管理ポータルの概要ビュー](../../media/LRS_AdminPortal_Summary_view.png)

> [!NOTE]
> LRSPowerUserAdminsGroup セキュリティグループに属している場合にのみ、[一括管理] メニューが表示されます。

### <a name="srs-room-information"></a>SRS ルーム情報

ポータルの [Room Info] セクションでは、個々の SRS ルームを表示および構成できます。 このセクションには、[設定]、[詳細]、[ログ]、[正常性] の4つのセクションがあります。

#### <a name="settings"></a>設定

[設定] セクションでは、ルームのパスワード、会議室タグ、および既定の音量レベルを設定できます。 これらの設定を構成した場合、変更は SRS コンソールを再起動した後にのみレプリケートされます。 SRS デバイスのシステム更新設定は、リリース15.12 以降を使用してのみ表示されます。

![Lync Room System 管理ポータルルームの設定](../../media/LRS_AdminPortal_RoomInfoSettings.png)

#### <a name="details"></a>詳細

[詳細] セクションには、SRS ルームの設定の読み取り専用の概要が表示されます。これには、最終更新日時が含まれます。次の会議。最終更新、メンテナンス、調整、既定のスピーカー、マイク、および着信音の設定。4.0SIP URI。画面の数と各画面の詳細。状態、およびアクティビティ。

![Lync Room System 管理ポータル詳細ビュー](../../media/LRS_AdminPortal_Detail_view.png)

#### <a name="troubleshooting"></a>トラブルシューティング

トラブルシューティングのセクションは、ログをリモートで収集し、指定した場所に保存するために使用できます。 SRS コンソール (SRS ユーザーインターフェイス) を再起動するか、システム全体を再起動することもできます。 ログを収集するには、指定された形式のフォルダーパスを指定し、SRS コンピューターアカウントに指定された書き込み権限がフォルダーにあることを確認します。 ログサイズが大きすぎる場合は、ログの収集が完了するまでに最大5分かかる場合があります。 ページを更新すると、最新の状態が表示されます。

#### <a name="health"></a>正常性

[正常性] セクションには、Skype for Business Server の接続、オーディオデバイス、ビデオデバイス、復元状態、画面デバイスの状態が視覚的に表示されます。

![Lync Room System 管理ポータルルームの正常性](../../media/LRS_AdminPortal_RoomInfoHealth.png)

### <a name="additional-notes-about-the-administrative-web-portal"></a>管理 Web ポータルに関するその他の注意事項

> [!NOTE]
>  設定変更は、SRS システムが再起動された後にのみ適用されます。 LRSApp アカウントのパスワードの有効期限が切れた場合、ルームの状態を表示することはできません。 >。 LRSAppuser アカウントのパスワードを有効期限切れにならないように構成するか、有効期限が近づいたときにパスワードを更新してください。 >、SRS 管理 web ポータルは社内展開でのみサポートされています。

### <a name="bulk-management"></a>一括管理

SRS ルームの一括管理は、高度な IT 管理者向けに設計された機能で、ワークフローを簡素化し、複数の部屋を一括で管理するための便利な時間を節約することができます。

この機能を確認するには、ユーザーが特別なセキュリティグループ**LRSPowerUserAdminsGroup**のメンバーとしてプロビジョニングされている必要があります。

一括管理のために選択できる SRS ルームの数に制限はありません。 ただし、一度に実行できる一括管理操作は1つだけです。

一括管理操作を実行するには、監視するルームを選択し、[一括管理] メニューをクリックします。

### <a name="frequently-asked-questions"></a>よく寄せられる質問

#### <a name="why-cant-i-sign-in-to-the-administrative-web-portal"></a>管理 web ポータルにサインインできないのはなぜですか?

を開くと、 https://localhost/lrs サインインページを表示できるようになりますが、サインイン情報を入力するときにサインインすることはできません。 この場合は、 https://FQDNofFEserver/SRS を開いて、管理 web ポータルにサインインする必要があります。

#### <a name="why-cant-i-see-srs-v1-in-the-administrative-web-portal"></a>管理 web ポータルで SRS v1 が表示されないのはなぜですか?

- 展開に SRS アカウントがあり、SRS の管理 Web ポータルの展開に関する推奨事項に従って作成されていることを確認してください。 Skype for Business Server で、SRS アカウントが、Enable-CsUser ではなく、enable-Csの会議室を使用してプロビジョニングされていることを確認してください。

- SRS アカウントを作成済みで、管理 web ポータルにアカウントが表示されていない場合は、「Skype for Business Server Logging tool」を使用してサーバーログを収集し、[**会議ポータル**] コンポーネントを選択した後、それを srs サポート連絡先に送信します。

- SRS アカウントを作成済みで、管理 web ポータルにアカウントが表示されない場合は、Fiddler を使用してクライアントログを収集し、ブラウザー開発ツールからコンソールログをコピーしてから、SRS サポート連絡先に送信します。 Web.config でトレースレベルの値を変更して、より詳細なログを取得することもできます。

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

#### <a name="why-cant-i-see-the-status-of-srs-in-the-administrative-web-portal"></a>管理 web ポータルで SRS の状態を確認できないのはなぜですか?

- LRSApp ユーザーアカウントの SIP が有効になっていることを確認します。

- それでも問題が解決しない場合は、D:\Tracing\LRSAdminLogs から SRS システムの**トレースログ**ファイルを収集して、 \, srs サポート連絡先に送信します。

#### <a name="why-cant-i-see-the-bulk-management-menus-for-srs-in-the-administrative-web-portal"></a>管理 web ポータルで SRS のバルク管理メニューが表示されないのはなぜですか?

LRSApp ユーザーアカウントが SIP 対応で、LRSPowerUserAdminsGroup セキュリティグループの一部であることを確認します。

#### <a name="does-the-srs-v1-administrative-web-portal-work-with-microsoft-teams-rooms"></a>SRS v1 管理 web ポータルは Microsoft Teams ルームと連携していますか?

いいえ。


