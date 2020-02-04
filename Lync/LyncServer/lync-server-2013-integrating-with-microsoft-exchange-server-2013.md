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
ms.openlocfilehash: f1467f6a570f83908eb5809f9493303bdc91c169
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41725857"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="integrating-microsoft-lync-server-2013-and-microsoft-exchange-server-2013"></a>Microsoft Lync Server 2013 と Microsoft Exchange Server 2013 の統合

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2014-07-09_

Exchange と Lync Server には、統合と互換性の長い履歴があります。 この統合は、それぞれのクライアントアプリケーションで最も顕著です。 たとえば、Lync のプレゼンス情報は Microsoft Outlook で報告できます。同様に、Lync では、Outlook の予定表を使って、プレゼンス情報を自動的に更新することができます。 (たとえば、会議がスケジュールされていることを予定表に示すときは、Lync によって状態が [取り込み中] に変更されることがあります)。Lync Server を実行するために Exchange を実行する必要はありませんが (またはその逆)、2つの製品を同時に使用することによって、"epitomizes" という用語の定義をまとめることはほとんどありません。

これは、Microsoft Lync Server 2013 と Microsoft Exchange Server 2013 のリリースに特に当てはまります。 Microsoft Exchange Server 2010 および Microsoft Lync Server 2010 で利用できるユニファイドメッセージング、IM、プレゼンスなどの機能に加えて、サーバー製品の2013リリースには、多くの新機能が含まれています。 これらの機能には、次のようなものがあります。

  - **Lync アーカイブの統合**。 Lync Server 2013 管理者でも、インスタントメッセージと Web 会議のトランスクリプトを SQL Server にアーカイブするオプションがあります (これらのトランスクリプトが Lync Server 2010 でアーカイブされた場合と同じです)。 また、管理者は、exchange のアーカイブと同じ方法で、トランスクリプトを Exchange 2013 にアーカイブすることを選ぶことができます。これらのトランスクリプトは個々のユーザーのメールボックスに保存されます。 つまり、すべての電子通信 (Exchange と Lync Server の両方) について単一のリポジトリを意味します。これにより、アーカイブされた通信を検索して、必要に応じて取得しやすくなります。

  - **統合連絡先ストア**。 Lync Server 2010 では、ユーザーは Outlook と Lync で個別の連絡先リストを管理する必要がありました。実際には、両方の製品で同じ連絡先が使用可能であることを確認するために、Outlook 用と Lync 用の連絡先リストの重複を管理する必要がありました。 ただし、Lync Server 2013 では、ユーザーの連絡先を Exchange 2013 とユニファイド連絡先ストアに保存できます。 1つの連絡先ストアを使用すると、ユーザーは1つの連絡先セットだけを保持できるため、Lync 2013、Outlook 2013、Outlook Web Access 2013 で利用できる連絡先と同じセットを使用できます。

  - **OWA からの Lync 会議のスケジュール設定**。 Lync Server 2013 および Exchange 2013 の統合機能を使用すると、ユーザーは Outlook Web Access 2013 から Lync 会議をスケジュールできます。

  - **高解像度の写真**。 Lync 2010 では、連絡先の小さな写真しか表示できませんでした。このような写真は Active Directory に保存されており、Active Directory では、保存された写真に48ピクセルのサイズの制限48を設けています。 ただし、Lync Server 2013 では、写真を Microsoft Exchange に保存することができます。これにより、648ピクセルから648ピクセルまでの高解像度の写真を使用できます。 このような高解像度の写真が表示されるように、Lync 2013 はアップグレードされています。

これらの新機能には Lync Server 2013 と Exchange 2013 の両方を使用する必要があることに注意してください。 また、これらの新機能を最大限に活用したいユーザーは、Lync Server 2013 および Exchange 2013 上のアカウントを持っている必要があります。また、最新バージョンのクライアントソフトウェア (Lync 2013 など) を使用している必要があります。 たとえば、統合連絡先ストアは、Lync Server 2010 を使っているユーザーは使用できません。同様に、高解像度の写真を Lync 2010 で表示することはできません。

このドキュメントでは、Lync Server 2013 および Exchange 2013 の統合について説明します。 アーカイブ統合やユニファイド連絡先ストアなどの新機能を有効にする手順について説明します。 このドキュメントでは、これら2つの製品の初期設定と構成について説明します。 Lync Server 2013 の展開の詳細については、「Lync Server [http://go.microsoft.com/fwlink/p/?LinkId=246127](http://go.microsoft.com/fwlink/p/?linkid=246127)2013 の技術センター」を参照してください。 Exchange 2013 の展開の詳細については、「Exchange [http://go.microsoft.com/fwlink/p/?LinkId=268528](http://go.microsoft.com/fwlink/p/?linkid=268528)2013 の技術センター」を参照してください。

<div>

## <a name="in-this-section"></a>このセクション中

[Microsoft Lync Server 2013 と Microsoft Exchange Server 2013 を統合するための前提条件](lync-server-2013-prerequisites-for-integrating-with-exchange-server-2013.md)

[Microsoft Lync Server 2013 および Microsoft Exchange Server 2013 でパートナーアプリケーションを構成する](lync-server-2013-configuring-partner-applications-in-lync-server-2013-and-exchange-server-2013.md)

[Microsoft Exchange Server 2013 アーカイブを使用するように Microsoft Lync Server 2013 を構成する](configuring-lync-server-2013-to-use-microsoft-exchange-server-2013-archiving.md)

[Microsoft SharePoint Server 2013 を構成してアーカイブされた Microsoft Lync Server 2013 データを検索する](lync-server-2013-configuring-microsoft-sharepoint-server-2013-to-search-for-archived-lync-server-2013-data.md)

[ユニファイド連絡先ストアを使用するように Microsoft Lync Server 2013 を構成する](lync-server-2013-configuring-lync-server-to-use-the-unified-contact-store.md)

[Microsoft Lync Server 2013 で高解像度の写真を使用するように構成する](lync-server-2013-configuring-the-use-of-high-resolution-photos.md)

[Microsoft Lync Server 2013 用 Microsoft Exchange Server 2013 ユニファイドメッセージングの構成ボイスメール](lync-server-2013-configuring-microsoft-exchange-server-2013-unified-messaging-for-lync-server-2013-voice-mail.md)

[Microsoft Lync Server 2013 と Microsoft Outlook Web App 2013 の統合](lync-server-2013-integrating-lync-server-and-outlook-web-app-2013.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

