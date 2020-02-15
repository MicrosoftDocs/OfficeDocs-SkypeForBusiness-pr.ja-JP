---
title: 'Lync Server 2013: Lync Server と Outlook Web App 2013 の統合'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Integrating Lync Server 2013 and Outlook Web App 2013
ms:assetid: 513d4cc7-aa87-4f68-b99d-d58b63bdf242
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688055(v=OCS.15)
ms:contentKeyID: 49733649
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 44de5139d3ad8f38c5177a18260045fda7abdeea
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42035309"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="integrating-microsoft-lync-server-2013-and-microsoft-outlook-web-app-2013"></a>Microsoft Lync Server 2013 と Microsoft Outlook Web App 2013 の統合

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2013-02-03_

Microsoft Outlook 2013 との統合に加えて、microsoft Lync Server 2013 は、microsoft Outlook Web App 2013 に完全に統合することができます。他にも、Outlook Web App へのインスタントメッセージングとプレゼンスの追加を行い、Outlook Web App と Microsoft Lync 2013 との間で統合連絡先リストを共有できるようにしています。 Lync Server 2013 と Outlook Web App を統合するためには、まず、ユニファイドコミュニケーション管理 API 4.0 ランタイムが Microsoft Exchange Server 2013 バックエンドサーバーにインストールされていることを確認する必要があります。 これを行うには、次のレジストリ値があるかどうかを調べます。

HKEY\_LOCAL\_MACHINE\\SYSTEM\\CurrentControlSet\\Services\\MSExchange OWA\\InstantMessaging\\ImplementationDLLPath

ImplementationDLLPath は、ファイルのフォルダーの場所をポイントする必要があります。 そうでない場合、またはレジストリ値が存在しない場合は、Microsoft ダウンロードセンターから、UCMA ランタイムセットアッププログラムをダウンロードしてインストールする<http://www.microsoft.com/download/details.aspx?id=34992>必要があります。 UCMA ランタイムをインストールする方法については、同じ web ページを参照してください。

**下位互換性**

Lync Server 2013 は、Microsoft Exchange Server 2010 バージョンのユニファイドメッセージングと Outlook Web App の両方に統合できます。 詳細については、「オンプレミスの Exchange UM を展開して Lync Server 2010 ボイス[http://technet.microsoft.com/library/gg398768.aspx](lync-server-2013-deploying-on-premises-exchange-um-to-provide-lync-server-2013-voice-mail.md)メールを提供する」の記事を参照してください。 Exchange 2010 と統合する場合は、統合連絡先ストアや Lync から Exchange へのアーカイブなどの Lync Server 固有の機能はありません。

Microsoft Lync 2013 は、Exchange 2010 および Outlook 2010 と組み合わせて使用することもできます。 ただし、今後も、統合連絡先ストアや高解像度写真などの新機能を Lync 2013 ユーザーが使用することはできません。 これらの新機能には、Lync Server 2013 と Exchange 2013 の両方が必要です。

**Outlook Web App 用の信頼されたアプリケーションプールを作成する**

Microsoft Exchange ユニファイドメッセージング呼び出しルーターサービスおよび Microsoft Exchange ユニファイドメッセージングサービスを同じコンピューターにインストールした場合、Outlook Web App 用の信頼されたアプリケーションプールを作成する必要はありません。 (これは、問題のサーバーが SipName UM ダイヤルプランをホストしていることを前提としています)。これらの両方のサービスをホストする単一のコンピューターを使用している場合は、このドキュメントの「 **Outlook Web App でのインスタントメッセージングの有効化**」というタイトルのセクションに進んでください。

Lync Server 2013 は、SipName UM ダイヤルプランをホストする Exchange サーバーを自動検出できます。これらのサーバーは、Lync Server 既知のサーバーの一覧に自動的に追加されます。 信頼されたアプリケーションプールを作成し、これらのサーバーを既知のサーバーの一覧に追加する必要はありません。 実際には、これを行うと、Outlook Web App の統合が動作しなくなります。

<div>


> [!NOTE]  
> これは、Lync Server トポロジでは、同じコンピューターに対して、autodiscovered エントリと手動で追加されたエントリという2つのエントリがあるためです。 この問題を解決するには、Outlook Web App を再度動作させるには、Windows PowerShell を使用して、サーバーの信頼できるプールと信頼されたアプリケーションエントリを削除します。 詳細については、 <A href="https://docs.microsoft.com/powershell/module/skype/Remove-CsTrustedApplicationPool">「new-cstrustedapplicationpool</A>および<A href="https://docs.microsoft.com/powershell/module/skype/Remove-CsTrustedApplication">「new-cstrustedapplication</A>コマンドレットのヘルプトピックを参照してください。



</div>

これら2つのサービスが別々のコンピューターで実行されている場合は、統合コミュニケーション管理 API 4.0 ランタイムがインストールされていることを確認した後に、Lync Server の信頼されたアプリケーションプールと、に関連付けられている信頼済みアプリケーションを作成する必要があります。Outlook Web App;これにより、サーバーが既知のサーバーの一覧に追加されます。 そのためには、まず、Lync Server 管理シェルで次のようなコマンドを実行します。

    New-CsTrustedApplicationPool -Identity atl-owa-001.litwareinc.com -Registrar atl-cs-001.litwareinc.com -Site Redmond -RequiresReplication $False

上記のコマンドでは、atl-owa-001.litwareinc.com は Outlook Web App プールの完全修飾ドメイン名です。これは、Outlook Web App へのアクセスを提供する証明書のサブジェクト名とサブジェクトの別名 (SAN) フィールドに表示される名前と同じである必要があります。 同様に、atl-cs-001.litwareinc.com は、新しい信頼されたアプリケーションプールをホストする Lync Server 2013 プールの完全修飾ドメイン名です。 また、指定されたサイト Redmond が Lync Server サイトの SiteID を表していることにも注意してください。 SiteID は、サイトの DisplayName と同じであるとは限りません。lync server 管理シェルから次のコマンドを実行することによって、Lync Server サイトの SiteIDs を取得できます。

    Get-CsSite | Select-Object DisplayName, SiteID

信頼されたアプリケーションプールを作成した後、次のようなコマンドを使用して、Outlook Web App のアプリケーション Id とポートを構成します。

    New-CsTrustedApplication -ApplicationId OutlookWebApp -TrustedApplicationPoolFqdn atl-owa-001.litwareinc.com  -Port 5199

前のコマンドで、ApplicationID は信頼済みアプリケーションを区別するために使用するわかりやすい識別子です。ApplicationID には、空白スペースや他の禁止されている文字が含まれていない任意のテキスト文字列を指定できます (有効な識別子を確実に作成するために、ApplicationID を指定するときには文字と数字だけを使用することをお勧めします)。Port パラメーターに割り当てる値も管理者が決定します。値として、使用可能な任意のネットワーク ポートを指定できます。

信頼されたアプリケーションを作成した後、次のコマンドを実行して、Lync Server トポロジへの変更を有効にする必要があります。

    Enable-CsTopology

また、Exchange クライアントアクセスとメールボックスサーバーをすべての SIP Uri ダイヤルプランに追加する必要があることにも注意してください。 これにより、Lync Server 用の ExUmRouting トポロジを使用して、サーバーが信頼できる SIP ピアとして構成されます。

**Outlook Web App でインスタントメッセージングを有効にする**

Lync Server が正しく構成されていれば、Outlook Web App の構成を開始できます。 このプロセスの最初の手順は、フロントエンドサーバー上のすべての Outlook Web App 仮想ディレクトリでインスタントメッセージングを有効にすることです。 (バックエンドサーバー上の仮想ディレクトリに対してインスタントメッセージングを有効にする必要はありません)。 実際には、バックエンドサーバーでインスタントメッセージングを有効にしないことをお勧めします。)Exchange 管理シェルで次のコマンドを実行することにより、クライアントアクセスサーバーでインスタントメッセージングを有効にできます。

    Get-OwaVirtualDirectory | Set-OwaVirtualDirectory -InstantMessagingEnabled $True -InstantMessagingType OCS

<div>


> [!NOTE]  
> 既定では、Outlook Web App をインストールすると、インスタントメッセージングが有効になります。つまり、InstantMessagingEnabled プロパティは True に設定されています。 ただし、インスタントメッセージングの種類を OCS に設定するには、上記のコマンドを引き続き実行する必要があります。 既定では、InstantMessagingType は None に設定されています。



</div>

次に、Outlook Web App の web.config ファイルに次の2行を追加する必要があります (このファイルは、\\通常、\\フォルダー\\C:\\Program\\Files Microsoft\\Exchange Server v15 で clientaccess Owa にあります)。 この2行は web.config ファイルの AppSettings \<\>ノードの下に追加する必要があります。この手順は、Outlook Web App がインストールされているバックエンドサーバーでのみ実行する必要があります。

    <add key="IMCertificateThumbprint" value="EA5A332496CC05DA69B75B66111C0F78A110D22d"/>
    <add key="IMServerName" value="atl-cs-001.litwareinc.com"/>

上記の例では、IMCertificateThumbprint の値は、バックエンドサーバーにインストールされている Exchange 2013 証明書の拇印である必要があります。 その情報を取得するには、Exchange 管理シェルから次のコマンドを実行します。

    Get-ExchangeCertificate

また、IMServerName に割り当てられた値が、Outlook Web App の信頼されたアプリケーションプールを作成した Lync Server プールの完全修飾ドメイン名であることにも注意してください。

Outlook Web App で使用する証明書は、Lync Server によって信頼されている証明書である必要があります。 証明書が Lync Server と Exchange の両方によって信頼されるようにする方法の1つは、内部証明機関を使用して、メールボックスサーバー上に証明書を作成し、そのサーバーの FQDN がサブジェクト名に使用されること、およびこの FQDN が t に表示されることを確認することです。「証明書の代替名」フィールド。 作成された証明書は、バックエンドサーバーにインポートできます。 最終的には、同じ証明書が Exchange ユニファイドメッセージングと Lync Server の間で2つの目的で使用されます。and 2) Outlook Web App と Lync Server の統合。

Web.config ファイルを更新したら、Outlook Web App プールをリサイクルするために、Exchange バックエンドサーバーで次のコマンドを実行する必要があります。

    C:\Windows\System32\Inetsrv\Appcmd.exe recycle apppool /apppool.name:"MSExchangeOWAAppPool"

リサイクル操作が正常に終了すると、Exchange 管理シェルに次のメッセージが表示されます。

    "MSExchangeOWAAppPool" successfully recycled

**Outlook Web App メールボックスポリシーの構成**

この時点で、次のコマンドを使用して、適切な Outlook Web App メールボックスポリシー (またはポリシー) でインスタントメッセージングを構成できます。 たとえば、次のコマンドをメールボックスサーバーの1つで実行すると、既定のポリシーでインスタントメッセージングが有効になります。

    Set-OwaMailboxPolicy -Identity "Default" -InstantMessagingEnabled $True -InstantMessagingType "OCS"

次のコマンドを実行すると、すべての Outlook Web App メールボックスポリシーでインスタントメッセージングが有効になります。

    Get-OwaMailboxPolicy | Set-OwaMailboxPolicy -InstantMessagingEnabled $True -InstantMessagingType "OCS"

メールボックスポリシーを有効にした後、そのポリシーによって管理されるすべてのユーザーは、Lync Server と Outlook Web App との完全な統合を行うことができます。その場合は次のようになります。

  - ユーザーが Exchange 2013 上にメールボックスを持っている。

  - ユーザーが Lync Server 2013 に対して有効になっている。

  - ユーザーが有効な SIP プロキシ アドレスを使用している。

**Outlook Web App でインスタントメッセージングを無効にする**

前述したように、Outlook Web App では既定でインスタントメッセージングが有効になっています。 これは、Outlook Web App と Lync Server を統合していない場合、ユーザーが Outlook Web App にログオンするたびに、空のプレゼンスアイコンとエラーメッセージが表示されることを意味します。 この問題を回避するには、次の Exchange 管理シェルコマンドを使用して、Outlook web App でインスタントメッセージングを無効にします。

    Get-OwaVirtualDirectory | Set-OwaVirtualDirectory -InstantMessagingEnabled $False

**Outlook Web App との統合の確認**

インスタントメッセージングとプレゼンスが Outlook Web App と統合されていることを確認するには、Outlook Web App 2013 にサインインします。 画面の右上隅に、Exchange 表示名が表示されます。 自分の名前の横にプレゼンスアイコンが表示されている場合 (たとえば、現在の状態が利用可能であることを示す緑色のアイコン)、Lync Server と Outlook Web App が正常に統合されたことを示します。

Outlook Web App に最初にサインオンした後、イベント ID 112 (およびソース MSExchange OWA) のイベントがメールボックスサーバーのイベントログに書き込まれているかどうかを確認します。 このイベントは、インスタントメッセージングエンドポイントマネージャーが正常に初期化されたことを示します。 インスタントメッセージングが動作していないように見える場合は、メールボックスサーバー上で\\、C: Program files\\Microsoft\\Exchange server\\v15 で\\Logging\\OWA\\InstantMessaging でログファイルを探します。 統合が失敗したことを示すログまたは InstantMessaging フォルダーのいずれかが存在しない場合。 その場合は、Lync Server の SIPStack トレース (すべてのレベルとすべてのフラグ) を使用して、統合が失敗した理由を特定してみることができます。

</div>

<span> </span>

</div>

</div>

</div>

