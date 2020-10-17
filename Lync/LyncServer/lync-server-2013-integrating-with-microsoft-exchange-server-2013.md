---
title: 'Lync Server 2013: Microsoft Exchange Server 2013 との統合'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Integrating Lync Server 2013 and Exchange Server 2013
ms:assetid: 795dc1c6-524f-4012-8b66-103b55198044
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688098(v=OCS.15)
ms:contentKeyID: 49733697
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 917ffc5103617c04a989ec91043a68fcce9f0320
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48498524"
---
# <a name="integrating-microsoft-lync-server-2013-and-microsoft-exchange-server-2013"></a>Microsoft Lync Server 2013 および Microsoft Exchange Server 2013 の統合

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2014-07-09_

Exchange と Lync Server の統合と互換性については、長い歴史があります。 この統合は、それぞれのクライアント アプリケーションの中でも最も重要なものです。 たとえば、Lync プレゼンス情報は Microsoft Outlook で報告できます。同様に、Lync は Outlook の予定表を使用して、そのプレゼンス情報を自動的に更新することができます。 (たとえば、Lync は、予定が設定された会議があることを予定表に表示するときに、いつでも状態を [取り込み中] に変更できます。)Lync Server を実行するために Exchange を実行する必要はありませんが (またはその逆も可能)、2つの製品を一緒に使用することによって、"より良い" という用語の定義が epitomizes されることはほとんどありません。

これは、Microsoft Lync Server 2013 と Microsoft Exchange Server 2013 のリリースでは特に当てはまります。 ユニファイドメッセージング、IM、プレゼンスなど、Microsoft Exchange Server 2010 および Microsoft Lync Server 2010 にある機能に加えて、サーバー製品の2013リリースにはいくつかの新機能が含まれています。 以下はその一例です。

  - **Lync アーカイブの統合**。 Lync Server 2013 では、管理者はインスタントメッセージングと Web 会議のトランスクリプトを SQL Server にアーカイブすることもできます (これらのトランスクリプトが Lync Server 2010 にアーカイブされた場合と同じ)。 また、管理者は、exchange 2013 にトランスクリプトをアーカイブすることを選択できます。これらのトランスクリプトは、Exchange が通信をアーカイブするのと同じ方法で、個々のユーザーのメールボックスに保存されます。 これは、すべての電子通信 (Exchange と Lync Server の両方) に対して単一のリポジトリを使用しているため、アーカイブされた通信を検索して取得し、必要に応じて取得するのがはるかに簡単になります。

  - **統合連絡先ストア**。 Lync Server 2010 では、ユーザーは Outlook と Lync で個別の連絡先リストを保持する必要がありました。実際には、両方の製品で同じ連絡先が使用可能であることを確認するために、Outlook 用と Lync 用に1つずつ、重複する連絡先リストを保持する必要がありました。 ただし、Lync Server 2013 では、ユーザーの連絡先を Exchange 2013 および統合連絡先ストアに格納できます。 単一の連絡先ストアを使用すると、1つの連絡先セットだけを保持し、Lync 2013、Outlook 2013、および Outlook Web Access 2013 でその連絡先の同じセットを使用できるようにすることができます。

  - **OWA からの Lync 会議のスケジュール**。 Lync Server 2013 と Exchange 2013 の統合により、ユーザーは Outlook Web Access 2013 から Lync 会議をスケジュールすることができます。

  - **高解像度写真** Lync 2010 は、連絡先の小さな写真しか表示できませんでした。これは、これらの写真は Active Directory に格納されており、Active Directory は、保存された写真に 48 48 ピクセルのサイズ制限を課すからです。 ただし、Lync Server 2013 では、写真を Microsoft Exchange に保存することができます。これにより、高解像度の写真を648ピクセル、648ピクセルにすることができます。 ご想像のとおり、Lync 2013 は、これらの高解像度の写真の表示を許可するようにアップグレードされています。

これらの新機能では、Lync Server 2013 と Exchange 2013 の両方を使用する必要があることに注意してください。 これに加えて、これらの新機能を十分に活用する必要があるユーザーは、Lync Server 2013 および Exchange 2013 のアカウントを持っており、最新バージョンのクライアントソフトウェア (Lync 2013 など) を使用している必要があります。 たとえば、Lync Server 2010 に所属しているユーザーは、統合連絡先ストアを使用できません。同様に、Lync 2010 に高解像度写真を表示することはできません。

このドキュメントでは、Lync Server 2013 と Exchange 2013 の統合について説明します。 アーカイブ統合、統合連絡先ストアなど、新機能を有効にするための詳細な手順について説明します。 このドキュメントでは、これら2つの製品の初期セットアップと構成について説明します。 Lync Server 2013 の展開の詳細については、「Lync Server 2013 Tech Center」を参照してください [https://go.microsoft.com/fwlink/p/?LinkId=246127](https://go.microsoft.com/fwlink/p/?linkid=246127) 。 Exchange 2013 の展開の詳細については、「Exchange 2013 の技術センター」を参照してください [https://go.microsoft.com/fwlink/p/?LinkId=268528](https://go.microsoft.com/fwlink/p/?linkid=268528) 。

<div>

## <a name="in-this-section"></a>このセクションの内容

[Microsoft Lync Server 2013 と Microsoft Exchange Server 2013 を統合するための前提条件](lync-server-2013-prerequisites-for-integrating-with-exchange-server-2013.md)

[Microsoft Lync Server 2013 と Microsoft Exchange Server 2013 でのパートナーアプリケーションの構成](lync-server-2013-configuring-partner-applications-in-lync-server-2013-and-exchange-server-2013.md)

[Microsoft Exchange Server 2013 アーカイブを使用するように Microsoft Lync Server 2013 を構成する](configuring-lync-server-2013-to-use-microsoft-exchange-server-2013-archiving.md)

[Microsoft SharePoint Server 2013 を構成して、アーカイブされた Microsoft Lync Server 2013 データを検索する](lync-server-2013-configuring-microsoft-sharepoint-server-2013-to-search-for-archived-lync-server-2013-data.md)

[統合連絡先ストアを使用するように Microsoft Lync Server 2013 を構成する](lync-server-2013-configuring-lync-server-to-use-the-unified-contact-store.md)

[Microsoft Lync Server 2013 で高解像度写真の使用を構成する](lync-server-2013-configuring-the-use-of-high-resolution-photos.md)

[Microsoft Lync Server 2013 ボイスメール用の Microsoft Exchange Server 2013 ユニファイドメッセージングの構成](lync-server-2013-configuring-microsoft-exchange-server-2013-unified-messaging-for-lync-server-2013-voice-mail.md)

[Microsoft Lync Server 2013 と Microsoft Outlook Web App 2013 の統合](lync-server-2013-integrating-lync-server-and-outlook-web-app-2013.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

