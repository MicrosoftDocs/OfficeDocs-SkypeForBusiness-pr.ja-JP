---
title: Microsoft Lync Server 2013 および Microsoft Outlook Web App 2013 の統合
TOCTitle: Microsoft Lync Server 2013 および Microsoft Outlook Web App 2013 の統合
ms:assetid: 513d4cc7-aa87-4f68-b99d-d58b63bdf242
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/JJ688055(v=OCS.15)
ms:contentKeyID: 49886957
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Microsoft Lync Server 2013 および Microsoft Outlook Web App 2013 の統合

 

_**トピックの最終更新日:** 2016-12-08_

Microsoft Outlook 2013 との統合に加え、Microsoft Lync Server 2013 は Microsoft Outlook Web App 2013 とも完全に統合できます。この統合により、インスタント メッセージングとプレゼンスが Outlook Web App に追加され、統合された連絡先リストを Outlook Web App と Microsoft Lync 2013 で共有できるようになります。Lync Server 2013 と Outlook Web App を統合するには、まず、Microsoft Exchange Server 2013 バックエンド サーバーに Unified Communications Managed API 4.0 Runtime がインストールされていることを確認する必要があります。これは、次のレジストリ値が存在するかどうかを調べることによって確認できます。

HKEY\_LOCAL\_MACHINE\\SYSTEM\\CurrentControlSet\\Services\\MSExchange OWA\\InstantMessaging\\ImplementationDLLPath

ImplementationDLLPath は、Microsoft.Rtc.Internal.Ucweb.dll ファイルのフォルダーの場所を指している必要があります。これを指していない場合やこのレジストリ値が存在しない場合は、Microsoft ダウンロード センター (<http://www.microsoft.com/ja-jp/download/details.aspx?id=34992>) から UCMA Runtime セットアップ プログラムをダウンロードし、インストールする必要があります。UCMA Runtime をインストールする方法に関する情報も、この Web ページに記載されています。

**下位互換性**

Lync Server 2013 は、ユニファイド メッセージングと Outlook Web App の両方の Microsoft Exchange Server 2010 バージョンと統合できます。詳細については、「内部設置型 Exchange UM を展開して Lync Server 2010 ボイス メールを提供する」([http://technet.microsoft.com/ja-jp/library/gg398768.aspx](lync-server-2013-deploying-on-premises-exchange-um-to-provide-lync-server-2013-voice-mail.md)) を参照してください。Exchange 2010 と統合すると、統合連絡先ストア、Lync から Exchange へのアーカイブなど、Lync Server 固有の機能は利用できません。

Microsoft Lync 2013 は、Exchange 2010 および Outlook 2010 と一緒に使用することもできます。ただし、この場合も、Lync 2013 ユーザーは、統合連絡先ストア、高解像度の写真などの新しい機能は使用できません。これらの新しい機能を使用するには、Lync Server 2013 と Exchange 2013 の両方が必要です。

**Outlook Web App 用の信頼済みアプリケーション プールを作成する**

Microsoft Exchange ユニファイド メッセージング通話ルーター サービスと Microsoft Exchange ユニファイド メッセージング サービスを同じコンピューターにインストールした場合は、Outlook Web App 用に信頼済みアプリケーション プールを作成する必要はありません (これは、該当するサーバーが SipName UM ダイヤル プランをホストすることを前提としています)。1 台のコンピューターでこの両方のサービスをホストする場合は、このドキュメントの「**Outlook Web App でインスタント メッセージングを有効にする**」セクションに進んでください。

Lync Server 2013 は、SipName UM ダイヤル プランをホストするすべての Exchange サーバーを自動検出できます。これらのサーバーは、Lync Server の既知のサーバー リストに自動的に追加されます。信頼済みアプリケーション プールを作成する必要はありません。また、これらのサーバーを既知のサーバー リストに追加する必要もありあせん。実際のところ、この操作を行うと、Outlook Web App 統合が機能しなくなります。

> [!NOTE]
> これは、Lync Server トポロジでは、同じコンピューターに対して自動検出エントリと手動追加エントリの 2 つのエントリが指定されるからです。この問題を修正し、Outlook Web App を再度動作させるには、Windows PowerShell を使用して、そのサーバーの信頼済みプールと信頼済みアプリケーションのエントリを削除します。詳細については、<a href="https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsTrustedApplicationPool">Remove-CsTrustedApplicationPool</a> および <a href="https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsTrustedApplication">Remove-CsTrustedApplication</a> コマンドレットのヘルプ トピックを参照してください。


この 2 つのサービスが個別のコンピューターで実行されている場合は、Unified Communications Managed API 4.0 Runtime がインストールされていることを確認したら、Outlook Web App に関連付けられた Lync Server の信頼済みアプリケーション プールと信頼済みアプリケーションを作成する必要があります。これにより、サーバーが既知のサーバー リストに追加されます。これを行うには、まず Lync Server 管理シェルから次のようなコマンドを実行します。

    New-CsTrustedApplicationPool -Identity atl-owa-001.litwareinc.com -Registrar atl-cs-001.litwareinc.com -Site Redmond -RequiresReplication $False

前のコマンドで、atl-owa-001.litwareinc.com は Outlook Web App プールの完全修飾ドメイン名です。これは、Outlook Web App へのアクセスを提供する証明書の "サブジェクト名" および "サブジェクトの別名 (SAN)" フィールドに表示される名前と同じ名前である必要があります。同様に、atl-cs-001.litwareinc.com は、新しい信頼済みアプリケーション プールをホストする Lync Server 2013 プールの完全修飾ドメイン名です。指定されているサイト Redmond は、Lync Server サイトの SiteID を表すことにも注意してください。SiteID は、サイトの DisplayName と必ずしも同じであるとは限りません。Lync Server サイトの SiteID を取得するには、Lync Server 管理シェルから次のコマンドを実行します。

    Get-CsSite | Select-Object DisplayName, SiteID

信頼済みアプリケーション プールを作成したら、次のようなコマンドを使用して、Outlook Web App のアプリケーション ID とポートを構成します。

    New-CsTrustedApplication -ApplicationId OutlookWebApp -TrustedApplicationPoolFqdn atl-owa-001.litwareinc.com  -Port 5199

前のコマンドで、ApplicationID は信頼済みアプリケーションを区別するために使用するわかりやすい識別子です。ApplicationID には、空白スペースや他の禁止されている文字が含まれていない任意のテキスト文字列を指定できます (有効な識別子を確実に作成するために、ApplicationID を指定するときには文字と数字だけを使用することをお勧めします)。Port パラメーターに割り当てる値も管理者が決定します。値として、使用可能な任意のネットワーク ポートを指定できます。

信頼済みアプリケーションを作成したら、次のコマンドを実行して、Lync Server トポロジに対する変更を有効にする必要があります。

    Enable-CsTopology

Exchange のクライアント アクセスおよびメールボックス サーバーを、SIP URI ダイヤル プランに追加する必要があることにも注意してください。これにより、これらのサーバーは、Lync Server の ExUmRouting トポロジで信頼済み SIP ピアとして構成されます。

**Outlook Web App でインスタント メッセージングを有効にする**

Lync Server が適切に構成されたら、Outlook Web App の構成を開始できます。このプロセスでは、まず、フロント エンド サーバーの Outlook Web App のすべての仮想ディレクトリで、インスタント メッセージングを有効にします (バックエンド サーバーの仮想ディレクトリでは、インスタント メッセージングを有効にする必要はありません。むしろ、バックエンド サーバーでは、インスタント メッセージングを有効にしないようにすることをお勧めします)。クライアント アクセス サーバーでインスタント メッセージングを有効にするには、Exchange 管理シェルから次のコマンドを実行します。

    Get-OwaVirtualDirectory | Set-OwaVirtualDirectory -InstantMessagingEnabled $True -InstantMessagingType OCS

> [!NOTE]
> Outlook Web App をインスールすると、インスタント メッセージングは既定で有効になっています。つまり、InstantMessagingEnabled プロパティは True に設定されています。ただし、上記のコマンドは、インスタント メッセージングの種類を OCS に設定する目的でも実行できます。既定では、InstantMessagingType は None に設定されています。


次に、Outlook Web App の Web.config ファイルに次の 2 行を追加する必要があります (通常、このファイルは C:\\Program Files\\Microsoft\\Exchange Server\\V15\\ClientAccess\\Owa フォルダーにあります)。この 2 行は、Web.config ファイルの \<AppSettings\> ノードの下に追加します。また、この手順は、Outlook Web App がインストールされているバックエンド サーバーでのみ実行することをお勧めします。

    <add key="IMCertificateThumbprint" value="EA5A332496CC05DA69B75B66111C0F78A110D22d"/>
    <add key="IMServerName" value="atl-cs-001.litwareinc.com"/>

前の例で、IMCertificateThumbprint の値は、バックエンド サーバーにインストールされた Exchange 2013 証明書の拇印である必要があります。この情報を取得するには、Exchange 管理シェルから次のコマンドを実行します。

    Get-ExchangeCertificate

IMServerName に割り当てる値は、Outlook Web App の信頼済みアプリケーション プールを作成した Lync Server プールの完全修飾ドメイン名であることにも注意してください。

Outlook Web App に使用する証明書は、Lync Server によって信頼された証明書である必要があります。証明書が Lync Server と Exchange の両方によって確実に信頼されるようにする 1 つの方法として、内部の証明書機関を使用してメールボックス サーバーに証明書を作成し、サーバー FQDN がサブジェクト名に使用されるように、そして、この FQDN が証明書の別名フィールドに表示されるようにするというものがあります。作成された証明書はバックエンド サーバーにインポートできます。最終的には、同じ証明書が 2 つの目的で使用されます。つまり、1) Exchange ユニファイド メッセージングと Lync Server の間を通信し、そして 2) Outlook Web App と Lync Server を統合するために使用されます。

Web.config ファイルを更新したら、Outlook Web App プールをリサイクルできるように、Exchange バックエンド サーバーで次のコマンドを実行します。

    C:\Windows\System32\Inetsrv\Appcmd.exe recycle apppool /apppool.name:"MSExchangeOWAAppPool"

リサイクル操作が正常に完了すると、Exchange 管理シェルに次のメッセージが表示されます。

    "MSExchangeOWAAppPool" successfully recycled

**Outlook Web App メール ボックス ポリシーを構成する**

この時点で、次のコマンドを使用して、適切な Outlook Web App メールボックス ポリシーでインスタント メッセージングを構成できます。たとえば、次のコマンドをメールボックス サーバーの 1 つで実行すると、既定のポリシーでインスタント メッセージングが有効になります。

    Set-OwaMailboxPolicy -Identity "Default" -InstantMessagingEnabled $True -InstantMessagingType "OCS"

また、次のコマンドを実行すると、すべての Outlook Web App メールボックス ポリシーでインスタント メッセージングが有効になります。

    Get-OwaMailboxPolicy | Set-OwaMailboxPolicy -InstantMessagingEnabled $True -InstantMessagingType "OCS"

メールボックス ポリシーを有効にすると、そのポリシーによって管理されるすべてのユーザーの Lync Server と Outlook Web App が完全に統合されます。ただし、次の条件を満たす必要があります。

  - ユーザーが Exchange 2013 のメールボックスを使用している。

  - ユーザーの Lync Server 2013 が有効になっている。

  - ユーザーが有効な SIP プロキシ アドレスを使用している。

**Outlook Web App でインスタント メッセージングを無効にする**

既に説明したように、インスタント メッセージングは Outlook Web App で既定で有効になっています。つまり、Outlook Web App を Lync Server と統合していない場合、ユーザーが Outlook Web App にログオンするたびに、空白のプレゼンス アイコンとエラー メッセージが表示されます。この問題が発生しないようにするには、次の Exchange 管理シェル コマンドを使用して、Outlook Web App でインスタント メッセージングを無効にします。

    Get-OwaVirtualDirectory | Set-OwaVirtualDirectory -InstantMessagingEnabled $False

**Outlook Web App との統合を確認する**

インスタント メッセージングとプレゼンスが Outlook Web App と統合されていることを確認するには、Outlook Web App 2013 にサインオンします。画面の右上隅に、Exchange 表示名が表示されます。名前の横にプレゼンス アイコン (たとえば、現在のステータスが "使用可能" であることを示す緑色のアイコン) がある場合は、Lync Server と Outlook Web App が適切に統合されていることを示します。

Outlook Web App に最初にサインオンしたら、イベント ID 112 (およびソース MSExchange OWA) のイベントが、メールボックス サーバーのイベント ログに書き込まれているかどうかを確認します。このイベントは、インスタント メッセージング エンドポイント マネージャーが適切に初期化されていることを示します。インスタント メッセージングが動作していないように思われる場合は、メールボックス サーバーの C:\\Program Files\\Microsoft\\Exchange server\\V15\\Logging\\OWA\\InstantMessaging フォルダーでログ ファイルを探します。Logging または InstantMessaging のどちらかのフォルダーが存在しない場合は、適切に統合されていないことを示します。この場合、統合が失敗した理由を特定するには、Lync Server で SIPStack トレースを使用します。

