---
title: 'Lync Server 2013: Microsoft Exchange Server 2013 との統合'
TOCTitle: Lync Server 2013 および Exchange Server 2013 の統合
ms:assetid: 795dc1c6-524f-4012-8b66-103b55198044
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/JJ688098(v=OCS.15)
ms:contentKeyID: 49887007
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Microsoft Lync Server 2013 および Microsoft Exchange Server 2013 の統合

 

_**トピックの最終更新日:** 2016-12-08_

Exchange と Lync Server には統合と互換性の長い歴史があります。この統合は、それぞれのクライアント アプリケーションの中でも最も重要なものです。たとえば、Lync のプレゼンス情報を Microsoft Outlook でレポートできます。同様に、Lync は、Outlook 予定表を使用してプレゼンス情報を自動的に更新できます (たとえば、Lync は予定表で会議が予定されている時間のステータスを取り込み中に変更できます)。Lync Server を実行するために Exchange を実行する必要はありませんが (またはその逆)、2 つの製品を併用すると "Better Together" という用語の定義が最適なものになることは確かです。

Microsoft Lync Server 2013 および Microsoft Exchange Server 2013 のリリースでは、これは特に当てはまります。Microsoft Exchange Server 2010 および Microsoft Lync Server 2010 のユニファイド メッセージング、IM、プレゼンスなどの機能に加えて、サーバー製品の 2013 リリースには多くの新機能が含まれています。以下はその一例です。

  - **Lync アーカイブの統合** 。Lync Server 2013 でも、管理者はインスタント メッセージングおよび Web 会議のトランスクリプトを SQL Server にアーカイブすることを選択できます (Lync Server 2010 と同じ方法です)。しかし、一方で、トランスクリプトを Exchange 2013 にアーカイブし、Exchange が通信をアーカイブするのと同じ方法で個別のユーザー メールボックスにトランスクリプトを格納することもできます。つまり、(Exchange および Lync Server からの) すべての電子通信に 1 つのリポジトリを使用でき、必要なときにアーカイブされた通信をいっそう簡単に検索して取得できるようになります。

  - **統合連絡先ストア** 。Lync Server 2010 では、ユーザーは Outlook と Lync で個別に連絡先を管理する必要がありました。実際、両方の製品で同じ連絡先を利用できるようにするには、Outlook 用と Lync 用に連絡先一覧を重複して管理することが必要でした。一方、Lync Server 2013 では、ユーザーの連絡先を Exchange 2013 および統合連絡先ストアに格納できます。1 つの連絡先ストアを使用することで、ユーザーは連絡先のセットを 1 つだけ管理すればよく、Lync 2013、Outlook 2013、Outlook Web Access 2013 で同じ連絡先セットを使用できます。

  - **OWA からの Lync 会議のスケジュール** 。 Lync Server 2013 と Exchange 2013 を統合したことで、ユーザーは Outlook Web Access 2013 から Lync 会議をスケジュールできます。

  - **高解像度の写真** 。Lync 2010 では、連絡先の小さい写真しか表示できませんでした。これは、写真が Active Directory に格納されており、Active Directory では格納される写真のサイズに 48 × 48 ピクセルの制限があるためでした。一方、Lync Server 2013 では、写真を Microsoft Exchange に保管できるので、最大 648 × 648 ピクセルの高解像度の写真を使用できます。また、Lync 2013 も高解像度写真を表示できるようにアップグレードされています。

これらの新機能を使用するには Lync Server 2013 と Exchange 2013 の両方が必要であることに注意してください。さらに、新機能を完全に利用するには、Lync Server 2013 および Exchange 2013 にアカウントがあり、最新バージョンのクライアント ソフトウェア (Lync 2013 など) を使用する必要があります。たとえば、Lync Server 2010 に所属しているユーザーは統合連絡先ストアを使用できません。同様に、Lync 2010 では高解像度の写真を表示できません。

このドキュメントでは、Lync Server 2013 と Exchange 2013 の統合に関して説明し、それにはアーカイブの統合や統合連絡先ストアなどの新機能を有効にする詳細な手順も含まれます。これら 2 つの製品の初期セットアップと構成については、このドキュメントでは説明しません。Lync Server 2013 の展開の詳細については、Lync Server 2013 TechCenter ([http://go.microsoft.com/fwlink/?linkid=246127\&clcid=0x411](http://go.microsoft.com/fwlink/?linkid=246127%26clcid=0x411)) を参照してください。Exchange 2013 の展開の詳細については、Exchange 2013 TechCenter ([http://go.microsoft.com/fwlink/?linkid=268528\&clcid=0x411](http://go.microsoft.com/fwlink/?linkid=268528%26clcid=0x411)) を参照してください。

## このセクション中

[Microsoft Lync Server 2013 および Microsoft Exchange Server 2013 の統合の前提条件](lync-server-2013-prerequisites-for-integrating-with-exchange-server-2013.md)

[Microsoft Lync Server 2013 および Microsoft Exchange Server 2013 のパートナー アプリケーションの構成](lync-server-2013-configuring-partner-applications-in-lync-server-2013-and-exchange-server-2013.md)

[Microsoft Exchange Server 2013 アーカイブを使用するための Microsoft Lync Server 2013 の構成](configuring-lync-server-2013-to-use-microsoft-exchange-server-2013-archiving.md)

[アーカイブされた Microsoft Lync Server 2013 データを検索するための Microsoft SharePoint Server 2013 の構成](lync-server-2013-configuring-microsoft-sharepoint-server-2013-to-search-for-archived-lync-server-2013-data.md)

[統合連絡先ストアを使用する Microsoft Lync Server 2013 の構成](lync-server-2013-configuring-lync-server-to-use-the-unified-contact-store.md)

[Microsoft Lync Server 2013 で高解像度写真を使用する構成](lync-server-2013-configuring-the-use-of-high-resolution-photos.md)

[Microsoft Lync Server 2013 ボイスメールに対する Microsoft Exchange Server 2013 ユニファイド メッセージングの構成](lync-server-2013-configuring-microsoft-exchange-server-2013-unified-messaging-for-lync-server-2013-voice-mail.md)

[Microsoft Lync Server 2013 および Microsoft Outlook Web App 2013 の統合](lync-server-2013-integrating-lync-server-and-outlook-web-app-2013.md)

