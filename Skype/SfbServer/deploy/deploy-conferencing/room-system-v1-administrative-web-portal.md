---
title: Skype for Business Server で SRS v1 管理 Web ポータルを展開する
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
description: Skype for Business Server の Skype Room Systems v1 (旧称 SRS v1、旧称 Lync Room System) 管理 Web ポータルは、組織が Skype Room Systems 会議室を管理するために使用できる web ポータルです。 管理者は、SRS v1 管理 Web ポータルを使用して、オーディオ/ビデオデバイスを監視するなどして、デバイスの正常性を監視することができます。 このポータルでは、管理者はリモートで診断情報を収集して、会議室の正常性を監視することができます。
ms.openlocfilehash: 558baac64bdb1e21ed710cb4dafb063ce75a62de
ms.sourcegitcommit: dd3a3ab4ddbdcfe772f30fb01ba3b97c45c43dd4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41768520"
---
# <a name="deploy-srs-v1-administrative-web-portal-in-skype-for-business-server"></a>Skype for Business Server で SRS v1 管理 Web ポータルを展開する

Skype for Business Server の Skype Room Systems v1 (旧称 SRS v1、旧称 Lync Room System) 管理 Web ポータルは、組織が Skype Room Systems 会議室を管理するために使用できる web ポータルです。 管理者は、SRS v1 管理 Web ポータルを使用して、オーディオ/ビデオデバイスを監視するなどして、デバイスの正常性を監視することができます。 このポータルでは、管理者はリモートで診断情報を収集して、会議室の正常性を監視することができます。

この機能を使用するには、SRS v1 管理 Web ポータルをすべての Skype for Business Server フロントエンドサーバーに展開する必要があります。 このガイドでは、管理者向けに SRS 管理 Web ポータルのインストールおよび設定方法について説明します。 これは、Skype for Business Server の管理について知識を持っている管理者、および Skype for Business Server トポロジを変更する管理者のユーザー権限を持つ管理者を対象としています。

SRS v1 管理 Web ポータルをサーバーに展開した後、管理者は、自分のコンピューターまたはノート pc からサイトにログオンして、状態の SRS v1 デバイスを確認できます。

> [!IMPORTANT]
> Skype for [Business Server 2015 の Microsoft Skype Room Systems V1 管理 Web ポータル](https://www.microsoft.com/en-us/download/details.aspx?id=46906)をダウンロードします。

このトピックでは、以下について説明します。

- [SRS v1 管理 Web ポータルの環境の構成](room-system-v1-administrative-web-portal.md#Config_Env)

- [SRS v1 管理 Web ポータルのインストール](room-system-v1-administrative-web-portal.md#Install_SRS)

- [SRS 管理 Web ポータルの使用](room-system-v1-administrative-web-portal.md#Use_Portal)

## <a name="configure-your-environment-for-the-srs-v1-administrative-web-portal"></a>SRS v1 管理 Web ポータルの環境の構成
<a name="Config_Env"> </a>

SRS v1 管理 Web ポータルを使用するには、次の前提条件をインストールまたは構成する必要があります。

> [!IMPORTANT]
> サーバーが Kerberos 認証と NTLM 認証の両方で構成されており、SRS がドメインに参加していないコンピューターで実行されている場合、Kerberos 認証は失敗し、管理ポータルで SRS のステータスを見ることはできません。この問題を解決するには、NTLM 認証、または NTLM 認証と TLS-DSK 認証の両方で (Kerberos を使って) サーバーを構成するか、SRS コンピューターをドメインに追加します。

1. Skype for business Server トポロジで Skype for Business Server の累積的な更新プログラムをインストールします。

    更新プログラムを入手したり、アプリに含まれている内容を確認したりするには、「 [Skype For Business Server 2015 の更新プログラム](https://support.microsoft.com/en-us/help/3061064/updates-for-skype-for-business-server-2015)」を参照してください。

2. SIP 対応の Active Directory ユーザーを作成します。

    SRS v1 管理 Web ポータルでは、これらの資格情報を使用して、Skype for Business Server から情報を照会します。 ここでの例のユーザー名は LRSApp です。

3. LRSSupportAdminGroup という名前の Active Directory セキュリティ グループを作成します。

    [グループのスコープ] が [グローバル]、[グループの種類] が [セキュリティ] のグループを作成します。このグループに追加される SIP 対応ユーザーは、部屋の一覧を参照したり、ログの収集などの特定のコマンドを実行したりすることができます。

4. LRSFullAccessAdminGroup という名前の Active Directory セキュリティ グループを作成します。

    [グループのスコープ] が [グローバル]、[グループの種類] が [セキュリティ] のグループを作成します。このグループに追加される SIP 対応ユーザーは、単一の Skype ルームで管理ポータルのすべての機能を使用できます。Skype ルームの一括管理のサポートを含める場合は、手順 5 を参照してください。

     ![セキュリティ グループの役割を持つ Admin グループの一覧](../../media/LRS_LRSFullAccessAdminGroup.png)

5. LRSPowerUserAdminsGroup という名前の Active Directory セキュリティ グループを作成します。

    [グループのスコープ] が [グローバル]、[グループの種類] が [セキュリティ] のグループを作成します。 このグループに追加された SIP 対応ユーザーは、Skype for Business 会議室の一括管理を含むすべての管理ポータル機能を使用することを許可されています。

6. LRSFullAccessAdminGroup を LRSSupportAdminGroup のメンバーとして追加します。

     ![LRSSupportAdminGroup プロパティ メンバー ページ](../../media/LRS_Add_LRSSupportAdminGroup.png)

7. LRSSupport という名前の SIP 対応の Active Directory ユーザーを作成します。 このユーザーを LRSSupportAdminGroup に追加します。

     ![LRSSupportAdminGroup プロパティ メンバー ページ](../../media/LRS_Add_LRS_SIP_SupportUser.png)

8. [Visual Studio 2010 sp1 と Visual Web Developer 2010 SP1 用の ASP.NET MVC 4 を](https://go.microsoft.com/fwlink/p/?LinkId=323967)インストールします。

## <a name="install-the-srs-v1-administrative-web-portal"></a>SRS v1 管理 Web ポータルのインストール
<a name="Install_SRS"> </a>

Skype for [Business Server 2015 の Microsoft Skype Room Systems V1 管理 Web ポータル](https://www.microsoft.com/en-us/download/details.aspx?id=46906)をダウンロードします。

SRS v1 管理 Web ポータルをインストールするには、次の手順を実行します。

1. Skype for Business Server 管理シェルで次のコマンドレットを実行して、信頼できるアプリケーションポートを構成します。

   ```powershell
   Set-CsWebServer -Identity POOLFQDN -MeetingRoomAdminPortalInternalListeningPort 4456 -MeetingRoomAdminPortalExternalListeningPort 4457
   ```

2. 会議室ポータルをインストールするには、**MeetingRoomPortalInstaller.msi** をダウンロードして管理者として実行します。

3. Web.config ファイルを次の場所から開きます。

    %Program Files%\Skype for Business Server 2015\Web Components\Meeting Room Portal\Int\Handler\

4. Web.config ファイルで、PortalUserName を「[SRS V1 管理 Web ポータルの環境を構成](room-system-v1-administrative-web-portal.md#Config_Env)する」セクションの「手順2で作成したユーザー名に変更します (手順は LRSApp の推奨名)。

    ```xml
    <add key="PortalUserName" value="sip:LRSApp@domain.com" />
    ```

5. SRS v1 管理ポータルは信頼済みアプリケーションであるため、ポータルの構成でパスワードを提示する必要はありません。このユーザーがローカル レジストラーとは別のレジストラーを使用している場合、Web.Config ファイルで次の行を追加してレジストラを指定する必要があります。

   ```xml
   <add key="PortalUserRegistrarFQDN" value="pool-xxxx.domain.com" />
   ```

6. 5061 以外のポートが使用されている場合は、Web.Config ファイルに次の行を追加します。

   ```xml
   <add key="PortalUserRegistrarPort" value="5061" />
   ```

### <a name="verify-installation-of-the-srs-administrative-web-portal"></a>SRS 管理 Web ポータルのインストールの検証

SRS v1 管理 Web ポータルのインストールを検証するには、次を行います。

1. フロントエンド サーバーで、次の URL を参照します。

    https://\<fe-サーバー\>/lrs

    下記の画像のように、エラーが表示されないようにします。

     ![Lync Room System、管理用ポータル サインイン画面](../../media/LRS_AdminPortalSignIn.png)

2. エラーが表示されない場合は、トポロジ内の他のいずれかのコンピューターから次の URL へのアクセスを試行します。

    https://\<fe-サーバー\>/lrs

    ページにアクセスするには、「[自動クライアントサインインのために必要な Dns レコード](https://go.microsoft.com/fwlink/p/?LinkId=318056)」の説明に従って DNS レコードを追加する必要があります。

## <a name="use-the-srs-administrative-web-portal"></a>SRS 管理 Web ポータルの使用
<a name="Use_Portal"> </a>

サーバーで SRS を展開した後、ブラウザーから SRS v1 管理 Web ポータルにサインインして、すべての SRS ルームの状態を確認できます。

### <a name="sign-in"></a>サインイン

1. 次の URL を参照します。

    https://\<fe-サーバー\>/lrs

2. LRSSupport アカウントの資格情報、または LRSSupportAdminGroup セキュリティ グループに追加されたアカウントを入力します。

![Lync Room System、管理用ポータル サインイン画面](../../media/LRS_AdminPortalSignIn.png)

### <a name="srs-administrative-web-portal-summary-page"></a>SRS 管理 Web ポータルの概要ページ

この概要ページには、サーバーで展開されたすべての SRS ルームに関する次の情報が表示されます。

- **タグ**管理者によってルームに付与されたカスタム名。 ルームの名前をクリックすると、ポータルでタグを設定できます。

- **正常性**会議室の正常性状態。会議室の [正常性] セクションの下に表示される、会議室の正常性状態。

- **次回の会議**次の会議がスケジュールされた日付と時刻。

- **SRS のバージョン、製造元、モデル**これらの値は、SRS で事前設定されています。 製造元によって、これらのフィールドは空白のままである場合があります。

- **最終更新**Web ページが最後に更新された時刻を表示します。

![Lync Room System、管理用ポータル概要ビュー](../../media/LRS_AdminPortal_Summary_view.png)

> [!NOTE]
> LRSPowerUserAdminsGroup セキュリティグループの一部である場合にのみ、一括管理メニューが表示されます。

### <a name="srs-room-information"></a>SRS ルーム情報

ポータルの [ルーム情報] セクションでは、個々の SRS ルームを表示および構成することができます。これには、[設定]、[詳細]、[ログ記録]、[動作状態] の 4 つのセクションがあります。

#### <a name="settings"></a>設定

[設定] セクションでは、パスワード、ルーム タグ、ルームの既定のボリューム レベルを設定できます。これらの設定を構成すると、SRS コンソールを再起動した後に、変更がレプリケートされます。SRS デバイスのシステム更新設定は、リリース 15.12 以降を使用してのみ表示されます。

![Lync Room System、管理用ポータル ルームの設定](../../media/LRS_AdminPortal_RoomInfoSettings.png)

#### <a name="details"></a>詳細

[詳細] セクションには、SRS ルームの設定の読み取り専用の概要が表示されます。これには、最終更新時刻が含まれます。次の会議最終更新、メンテナンス、調整。既定のスピーカー、マイク、着信音の設定バージョンSIP URI画面の数と各画面の詳細。状態、アクティビティ。

![Lync Room System、管理用ポータル詳細ビュー](../../media/LRS_AdminPortal_Detail_view.png)

#### <a name="troubleshooting"></a>トラブルシューティング

[トラブルシューティング] セクションを使用して、ログをリモートで収集し、指定した場所に保存できます。また、SRS コンソール (SRS ユーザー インターフェイス) を再起動したり、システム全体を再起動したりすることもできます。ログを収集するには、フォルダー パスを指定された形式で入力して、そのフォルダーに対して SRS コンピューターのアカウントに与えられた書き込みアクセス許可が設定されていることを確認します。ログ サイズが大きすぎる場合は、ログの収集を完了するのに最大約 5 分かかる可能性があります。ページを更新すると、最新の状態が表示されます。

#### <a name="health"></a>動作状態

[正常性] セクションには、Skype for Business Server 接続、オーディオデバイス、ビデオデバイス、復元の状態、画面デバイスの正常性が視覚的に示されます。

![Lync Room System、管理用ポータル ルームの正常性](../../media/LRS_AdminPortal_RoomInfoHealth.png)

### <a name="additional-notes-about-the-administrative-web-portal"></a>管理 Web ポータルに関する追加の注意事項

> [!NOTE]
>  設定の変更は、SRS システムが再起動された後にのみ適用されます。 LRSApp アカウントのパスワードの有効期限が切れた場合、会議室の状態を表示することはできません。 > LRSAppuser account のパスワードを無期限に設定するか、有効期限が近いときにパスワードを更新して > ください。 SRS 管理 web ポータルは、オンプレミスの展開でのみサポートされます。

### <a name="bulk-management"></a>一括管理 

SRS ルームの一括管理は、高度な IT 管理者向けに設計された機能で、ワークフローを簡素化し、管理者が時間を節約できる便利なツールを利用してリモートで複数のルームを一括方式で管理できるようにします。

この機能を確認するには、ユーザーは特別なセキュリティ グループ **LRSPowerUserAdminsGroup** のメンバーとして配備されている必要があります。

一括管理のために選択できる SRS ルームの数に制限はありません。ただし、同時に実行できる一括管理の操作は 1 つのみです。

一括管理の操作を実行するには、監視するルームを選択してから一括管理メニュー上でクリックします。

### <a name="frequently-asked-questions"></a>よく寄せられる質問

#### <a name="why-cant-i-sign-in-to-the-administrative-web-portal"></a>管理 web ポータルにサインインできないのはなぜですか?

を開くhttps://localhost/lrsと、サインインページが表示されますが、資格情報を入力するときにサインインすることはできません。 この場合、管理 web ポータルにhttps://FQDNofFEserver/SRSサインインするには、を開く必要があります。

#### <a name="why-cant-i-see-srs-v1-in-the-administrative-web-portal"></a>管理 web ポータルに SRS v1 が表示されないのはなぜですか?

- 展開で SRS アカウントを取得していること、それらのアカウントが 	SRS 管理 Web ポータルの展開の推奨事項に従って作成されていることを確認してください。 Skype for Business Server で、お使いの SRS アカウントが、CsUser を有効にしていることを確認します。

- SRS アカウントを作成していて、そのアカウントが管理 web ポータルに表示されない場合は、「Skype for Business Server ログツールを使って、**会議ポータル**コンポーネントが選択されている状態でサーバーログを収集し、srs サポートの連絡先に送信します。

- SRS アカウントを作成しても、管理 Web ポータルでそのアカウントを確認できない場合は、Fiddler を使用してクライアント ログを収集し、ブラウザー開発ツールからコンソール ログもコピーして、それらのログを SRS サポートの連絡先に送信してください。より詳細なログを取得するために Web.config でトレース レベルの値を変更することもできます。

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

#### <a name="why-cant-i-see-the-status-of-srs-in-the-administrative-web-portal"></a>管理 web ポータルで SRS の状態が表示されないのはなぜですか?

- LRSApp ユーザー アカウントが SIP 対応であることを確認してください。

- それでも問題が解決されない場合は、D:\Tracing\LRSAdminLogs\,から srs システムの**Trace .log**ファイルを収集して、srs のサポート担当者に送信します。

#### <a name="why-cant-i-see-the-bulk-management-menus-for-srs-in-the-administrative-web-portal"></a>管理 web ポータルで SRS の一括管理メニューが表示されないのはなぜですか?

LRSApp のユーザーアカウントが SIP 対応であり、LRSPowerUserAdminsGroup セキュリティグループの一部であることを確認します。

#### <a name="does-the-srs-v1-administrative-web-portal-work-with-microsoft-teams-rooms"></a>SRS v1 管理 web ポータルは Microsoft Teams のルームで動作しますか?

いいえ。


