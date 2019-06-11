---
title: 'Lync Server 2013: Lync Server と Outlook Web App 2013 の統合'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Integrating Lync Server 2013 and Outlook Web App 2013
ms:assetid: 513d4cc7-aa87-4f68-b99d-d58b63bdf242
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688055(v=OCS.15)
ms:contentKeyID: 49733649
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 31a25e1d0a6410171201af578d6b28f496468e06
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34832985"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="integrating-microsoft-lync-server-2013-and-microsoft-outlook-web-app-2013"></a>Microsoft Lync Server 2013 と Microsoft Outlook Web App 2013 の統合

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2013-02-03_

Microsoft Outlook 2013 との統合に加えて、microsoft Lync Server 2013 は microsoft Outlook Web App 2013 と完全に統合することができます。この操作を行うと、Outlook Web App にインスタントメッセージとプレゼンスが追加され、Outlook Web App と Microsoft Lync 2013 の間でユニファイド連絡先リストを共有できるようになります。 Lync Server 2013 と Outlook Web App を統合するには、まずユニファイドコミュニケーションマネージ API 4.0 ランタイムが Microsoft Exchange Server 2013 バックエンドサーバーにインストールされていることを確認する必要があります。 この操作を行うには、次のレジストリ値が存在することを確認します。

HKEY\_LOCAL\_MACHINE\\SYSTEM\\CurrentControlSet\\Services\\MSExchange OWA\\InstantMessaging\\ImplementationDLLPath

ImplementationDLLPath は、Microsoft.Rtc.Internal.Ucweb.dll ファイルのフォルダーの場所をポイントします。 見つからない場合、またはレジストリ値が存在しない場合は、Microsoft ダウンロードセンターから、UCMA ランタイムセットアッププログラムをダウンロードしてインストールする必要<http://www.microsoft.com/en-us/download/details.aspx?id=34992>があります。 UCMA Runtime のインストール方法についても、この Web ページに記載されています。

**下位互換性**

Lync Server 2013 は、Microsoft Exchange Server 2010 バージョンのユニファイドメッセージングと Outlook Web App に統合できます。 詳細については、「オンプレミスの Exchange UM を展開して Lync Server 2010 ボイス[http://technet.microsoft.com/en-us/library/gg398768.aspx](lync-server-2013-deploying-on-premises-exchange-um-to-provide-lync-server-2013-voice-mail.md)メールを提供する」の記事を参照してください。 Exchange 2010 と統合する場合、統合連絡先ストアや Lync 間アーカイブなどの Lync Server 固有の機能は使用できません。

Microsoft Lync 2013 は、Exchange 2010 および Outlook 2010 と組み合わせて使用することもできます。 ただし、統合連絡先ストアや高解像度写真などの新機能は、Lync 2013 ユーザーには利用できません。 これらの新しい機能には、Lync Server 2013 と Exchange 2013 の両方が必要です。

**Outlook Web App 用の信頼済みアプリケーション プールを作成する**

Microsoft Exchange ユニファイドメッセージングコールルータサービスと Microsoft Exchange ユニファイドメッセージングサービスを同じコンピューターにインストールしている場合、Outlook Web App 用の信頼されたアプリケーションプールを作成する必要はありません。 (これは、問題のサーバーが SipName UM ダイヤルプランをホストしていることを前提としています)。これらの両方のサービスをホストするために単一のコンピューターを使用している場合は、このドキュメントの「 **Outlook Web App でインスタントメッセージングを有効**にする」のセクションに進んでください。

Lync Server 2013 は、SipName UM ダイヤルプランをホストしているすべての Exchange サーバーを自動検出できます。これらのサーバーは、Lync Server の [既知のサーバー] リストに自動的に追加されます。 信頼されたアプリケーションプールを作成し、これらのサーバーを [既知のサーバー] リストに追加する必要はありません。 実際には、Outlook Web App の統合が機能しなくなります。

<div>


> [!NOTE]  
> これは、Lync Server トポロジで、autodiscovered エントリと手動で追加されたエントリの2つのエントリが同じコンピューターに設定されていることが原因です。 この問題を修正し、Outlook Web App を再度動作させるには、Windows PowerShell を使用して、そのサーバーの信頼済みプールと信頼済みアプリケーションのエントリを削除します。 詳細については、<A href="https://docs.microsoft.com/powershell/module/skype/Remove-CsTrustedApplicationPool">Remove-CsTrustedApplicationPool</A> および <A href="https://docs.microsoft.com/powershell/module/skype/Remove-CsTrustedApplication">Remove-CsTrustedApplication</A> コマンドレットのヘルプ トピックを参照してください。



</div>

これら2つのサービスが別々のコンピューターで実行されている場合は、ユニファイドコミュニケーションのマネージ API 4.0 ランタイムがインストールされていることを確認した後、Lync Server の信頼済みアプリケーションプールと、それに関連付けられた信頼済みアプリケーションを作成する必要があります。Outlook Web Appこれにより、サーバーが既知のサーバーの一覧に追加されます。 そのためには、まず、Lync Server 管理シェルで次のようなコマンドを実行します。

    New-CsTrustedApplicationPool -Identity atl-owa-001.litwareinc.com -Registrar atl-cs-001.litwareinc.com -Site Redmond -RequiresReplication $False

上記のコマンドでは、atl-owa-001.litwareinc.com は Outlook Web App pool の完全修飾ドメイン名です。これは、Outlook Web App へのアクセスを提供する証明書のサブジェクト名とサブジェクト代替名 (SAN) フィールドに表示される名前と同じである必要があります。 同様に、atl-cs-001.litwareinc.com は、新しい信頼されたアプリケーションプールをホストする Lync Server 2013 プールの完全修飾ドメイン名です。 また、指定したサイト Redmond が、Lync Server サイトの SiteID を表していることにも注目してください。 SiteID は、サイトの DisplayName と同じであるとは限りません。lync server の管理シェルから次のコマンドを実行して、Lync Server サイトの SiteIDs を取得できます。

    Get-CsSite | Select-Object DisplayName, SiteID

信頼済みアプリケーション プールを作成したら、次のようなコマンドを使用して、Outlook Web App のアプリケーション ID とポートを構成します。

    New-CsTrustedApplication -ApplicationId OutlookWebApp -TrustedApplicationPoolFqdn atl-owa-001.litwareinc.com  -Port 5199

前のコマンドで、ApplicationID は信頼済みアプリケーションを区別するために使用するわかりやすい識別子です。ApplicationID には、空白スペースや他の禁止されている文字が含まれていない任意のテキスト文字列を指定できます (有効な識別子を確実に作成するために、ApplicationID を指定するときには文字と数字だけを使用することをお勧めします)。Port パラメーターに割り当てる値も管理者が決定します。値として、使用可能な任意のネットワーク ポートを指定できます。

信頼できるアプリケーションを作成した後、次のコマンドを実行して、Lync Server トポロジの変更を有効にする必要があります。

    Enable-CsTopology

また、すべての SIP Uri ダイヤルプランに Exchange クライアントアクセスとメールボックスサーバーを追加する必要があることに注意してください。 これにより、サーバーが、Lync Server の ExUmRouting topology で信頼できる SIP ピアとして構成されます。

**Outlook Web App でインスタント メッセージングを有効にする**

Lync サーバーが正しく構成されている場合は、Outlook Web App の構成を開始できます。 このプロセスの最初の手順は、フロントエンドサーバー上のすべての Outlook Web App 仮想ディレクトリでインスタントメッセージングを有効にすることです。 (バックエンドサーバーの仮想ディレクトリに対してインスタントメッセージングを有効にする必要はありません。 実際には、バックエンドサーバでインスタントメッセージを有効にしないことをお勧めします。)Exchange 管理シェル内から次のコマンドを実行して、クライアントアクセスサーバーでインスタントメッセージングを有効にすることができます。

    Get-OwaVirtualDirectory | Set-OwaVirtualDirectory -InstantMessagingEnabled $True -InstantMessagingType OCS

<div>


> [!NOTE]  
> Outlook Web App をインストールすると、インスタント メッセージングは既定で有効になります。つまり、InstantMessagingEnabled プロパティは True に設定されます。ただし、上記のコマンドは、インスタント メッセージングの種類を OCS に設定する目的でも実行できます。既定では、InstantMessagingType は None に設定されています。



</div>

次に、次の2行を Outlook Web App web.config ファイルに追加する必要があります (このファイルは、通常\\、C\\:\\Program Files\\Microsoft\\Exchange Server\\V15 clientaccess Owa) に含まれています。 この2行は、web.config ファイルの\<AppSettings\>ノードの下に追加する必要があります。この手順は、Outlook Web App がインストールされているバックエンドサーバーでのみ実行する必要があります。

    <add key="IMCertificateThumbprint" value="EA5A332496CC05DA69B75B66111C0F78A110D22d"/>
    <add key="IMServerName" value="atl-cs-001.litwareinc.com"/>

上の例では、IMCertificateThumbprint の値はバックエンドサーバーにインストールされている Exchange 2013 証明書の拇印である必要があります。 この情報を取得するには、Exchange 管理シェルから次のコマンドを実行します。

    Get-ExchangeCertificate

また、IMServerName に割り当てられている値が、Outlook Web App の信頼されたアプリケーションプールを作成した Lync Server プールの完全修飾ドメイン名であることに注意してください。

Outlook Web App で使用する証明書は、Lync Server によって信頼されている証明書である必要があります。 証明書が Lync Server と Exchange の両方によって信頼されるようにする方法の1つは、内部の証明機関を使ってメールボックスサーバーで証明書を作成し、その FQDN がサブジェクト名に使用され、この FQDN が t に表示されるようにすることです。証明書の代替名フィールド。 作成された証明書はバックエンド サーバーにインポートできます。 最終的には、同じ証明書が Exchange ユニファイドメッセージングと Lync Server 間の通信という2つの目的で使用されることになります。および 2) Outlook Web App と Lync Server の統合。

Web.config ファイルの更新後、Exchange バックエンドサーバーで次のコマンドを実行して、Outlook Web App pool をリサイクルする必要があります。

    C:\Windows\System32\Inetsrv\Appcmd.exe recycle apppool /apppool.name:"MSExchangeOWAAppPool"

リサイクル操作が成功すると、Exchange 管理シェルに次のメッセージが表示されます。

    "MSExchangeOWAAppPool" successfully recycled

**Outlook Web App メール ボックス ポリシーを構成する**

この時点で、次のコマンドを使用して、適切な Outlook Web App メールボックス ポリシーでインスタント メッセージングを構成できます。たとえば、次のコマンドをメールボックス サーバーの 1 つで実行すると、既定のポリシーでインスタント メッセージングが有効になります。

    Set-OwaMailboxPolicy -Identity "Default" -InstantMessagingEnabled $True -InstantMessagingType "OCS"

また、次のコマンドを実行すると、すべての Outlook Web App メールボックス ポリシーでインスタント メッセージングが有効になります。

    Get-OwaMailboxPolicy | Set-OwaMailboxPolicy -InstantMessagingEnabled $True -InstantMessagingType "OCS"

メールボックスポリシーを有効にすると、そのポリシーによって管理されるすべてのユーザーは、次のような Lync Server と Outlook Web App の間で完全に統合されます。

  - ユーザーが Exchange 2013 上にメールボックスを持っている。

  - ユーザーが Lync Server 2013 用に有効になっている。

  - ユーザーが有効な SIP プロキシ アドレスを使用している。

**Outlook Web App でインスタント メッセージングを無効にする**

既に説明したように、インスタント メッセージングは Outlook Web App で既定で有効になっています。 つまり、Outlook Web App を Lync Server と統合していない場合は、ユーザーが Outlook Web App にログオンするたびに、空白のプレゼンスアイコンとエラーメッセージが表示されます。 この問題を回避するには、次の Exchange 管理シェルコマンドを使用して、Outlook web App でインスタントメッセージングを無効にします。

    Get-OwaVirtualDirectory | Set-OwaVirtualDirectory -InstantMessagingEnabled $False

**Outlook Web App との統合を確認する**

インスタント メッセージングとプレゼンスが Outlook Web App と統合されていることを確認するには、Outlook Web App 2013 にサインオンします。 画面の右上隅に、Exchange 表示名が表示されます。 名前の横にプレゼンスアイコンが表示されている場合 (たとえば、現在の状態が利用可能であることを示す緑色のアイコン)、Lync Server と Outlook Web App が正常に統合されたことを示します。

Outlook Web App に最初にサインオンしたら、イベント ID 112 (およびソース MSExchange OWA) のイベントが、メールボックス サーバーのイベント ログに書き込まれているかどうかを確認します。 このイベントは、インスタント メッセージング エンドポイント マネージャーが適切に初期化されていることを示します。 インスタントメッセージングが機能していないように見える場合は、メールボックスサーバーで、\\フォルダー C: Program files\\Microsoft\\Exchange server\\V15\\Logging\\OWA\\InstantMessaging のログファイルを探します。 Logging または InstantMessaging のどちらかのフォルダーが存在しない場合は、適切に統合されていないことを示します。 その場合は、Lync Server (すべてのレベルとすべてのフラグ) で SIPStack トレースを使用して、統合に失敗した理由を特定してください。

</div>

<span> </span>

</div>

</div>

</div>

