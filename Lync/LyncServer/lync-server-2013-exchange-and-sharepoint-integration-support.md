---
title: 'Lync Server 2013: Exchange Server および SharePoint の統合のサポート'
TOCTitle: Exchange Server および SharePoint の統合のサポート
ms:assetid: 72bf8aa5-55b1-4851-8a59-c96bf85d215a
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/JJ205005(v=OCS.15)
ms:contentKeyID: 48272448
ms.date: 01/20/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 の Exchange Server および SharePoint の統合のサポート

 

_**トピックの最終更新日:** 2017-01-18_

Lync Server 2013 と Lync 2013 は、Office 2013、Exchange 2013、SharePoint (これらの製品と統合している場合) など、他のアプリケーションやサーバー製品と安全かつシームレスに通信できます。Lync Server 2013 と Office は、Lync のインスタント メッセージング (IM)、強化されたプレゼンス、テレフォニー、および会議の各機能をユーザーに提供します。Office ユーザーは、Outlook 2013 のメッセージングおよびコラボレーション クライアントや他の Office プログラム内で、または Microsoft SharePoint Server 2010 ページから Lync 機能にアクセスできます。また、ユーザーは Outlook の \[会話履歴\] フォルダーにある Lync の対話の記録を表示できます。Exchange 2013 または Exchange Online と統合されている場合、Lync Server 2013 は以下もサポートします。

  - 統合連絡先ストア。ユーザーはすべての連絡先情報を Exchange 2013 または Exchange Online に保存できるので、その情報は Lync 2013、Exchange、Outlook、および Outlook Web App 間でグローバルに利用できます。

  - 会話履歴と Web 会議履歴。これらは Exchange ユーザー フォルダーに保存されます。

  - IM や会議のコンテンツなど、Lync からアーカイブされたコンテンツは、Exchange ストレージに保存できます。

> [!NOTE]
> Lync Server 2013 は、以前のバージョンの Microsoft Exchange Server および SharePoint との統合をサポートしていますが、すべての機能がこうした以前のバージョンでサポートされているわけではありません (例: アーカイブ ストレージと Microsoft Exchange との統合)。<br />
> ユーザーを Exchange 2013 に移行する場合は、移行が完了するまで、Exchange ストレージと Lync Server ストレージの両方を暫定的に使用できます。Exchange と Lync Server の両方のストレージの永続的な使用は、サポートされていません。


Lync Server 2013 を Exchange 2013 および SharePoint Server と統合するには、Lync Server 2013、Microsoft Exchange Server、および SharePoint Server を実行しているサーバー間のサーバー間認証が必要です。Lync Server 2013 では、サーバー間の認証および承認のために OAuth (Open Authorization) プロトコルをサポートしています。2 台の Microsoft サーバーの間での社内のサーバー間認証では、サードパーティのトークン サーバーを使用する必要がありません。Lync Server 2013、Exchange 2013、および SharePoint には、認証の目的で相互に使用できる組み込みのトークン サーバーが存在します。たとえば、Lync Server 2013 は、単独でセキュリティ トークンを発行および署名でき、Exchange 2013 との通信時にそのトークンを使用します。この場合、サードパーティのトークン サーバーを使用する必要はありません。

Lync Server 2013 では、2 つのサーバー間認証シナリオをサポートしています。これらのシナリオには、以下の間でのサーバー間認証の構成が含まれます。

  - Lync Server 2013 の社内インストールと、Exchange 2013 や SharePoint Server の社内インストール。

  - Office コンポーネントどうしのペア (Microsoft Exchange 365 と Microsoft Lync Server 365、または Microsoft Lync Server 365 と Microsoft SharePoint 365 など)。

> [!NOTE]
> 社内サーバーと Office 365 コンポーネントの間のサーバー間認証は、この Lync Server 2013 リリースではサポートされていません。これは、とりわけ Lync Server 2013 の社内インストールと Microsoft Exchange 365 との間のサーバー間認証を設定できないことを意味します。


サーバー間認証の詳細については、「展開」または「操作」のドキュメントの「[Lync Server 2013 でのサーバー間認証 (Oauth) およびパートナー アプリケーションの管理](lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md)」を参照してください。

