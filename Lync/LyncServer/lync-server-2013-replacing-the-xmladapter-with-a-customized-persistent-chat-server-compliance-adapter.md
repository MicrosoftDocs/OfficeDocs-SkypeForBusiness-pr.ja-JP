---
title: 'Lync Server 2013: カスタマイズされた常設チャット Server コンプライアンスアダプターを使用した Xml アダプターの置き換え'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Replacing the XmlAdapter with a customized Persistent Chat Server Compliance adapter
ms:assetid: 2cb70db2-663f-40a6-abcf-89ea7d4a8b65
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ680106(v=OCS.15)
ms:contentKeyID: 49558152
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3d26e470438dc8a79dbaa3944c05ad4158cafe44
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34823141"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="replacing-the-xmladapter-with-a-customized-persistent-chat-server-compliance-adapter-in-lync-server-2013"></a>Lync Server 2013 での、カスタマイズされた常設チャットサーバーのコンプライアンスアダプターを使用した Xml アダプターの置き換え

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2012-11-01_

常設チャットサーバーと共にインストールされている XmlAdapter を使う代わりに、カスタムアダプターを作成することができます。 記述するには、**IComplianceAdapter** インターフェイスを実装するパブリック クラスを含む .NET Framework アセンブリを提供する必要があります。 このアセンブリは、常設チャットサーバープールの各サーバーの常設チャットサーバーのインストールフォルダーに配置する必要があります。 任意のコンプライアンス サーバーからアダプターにコンプライアンス データを提供できますが、コンプライアンス サーバーからアダプターの複数のインスタンスに対して重複するコンプライアンス データを提供することはできません。

<div>

## <a name="implementing-the-icomplianceadapter-interface"></a>IComplianceAdapter インターフェイスの実装

インターフェイスは、名前空間`Microsoft.Rtc.Internal.Chat.Server.Compliance`の対応する .dll アセンブリで定義されます。 このインターフェイスには、カスタム アダプターが実装する必要のある 2 つのメソッドが定義されています。

    void SetConfig(AdapterConfig config)

常設チャットのコンプライアンスサーバーは、アダプターが最初に読み込まれたときにこのメソッドを呼び出します。 に`AdapterConfig`は、コンプライアンスアダプターに関連する常設チャットのコンプライアンス構成が含まれています。

    void Translate(ConversationCollection conversations)

常設チャットのコンプライアンスサーバーは、翻訳する新しいデータがある限り、定期的な間隔でこのメソッドを呼び出します。 この時間間隔は、常設チャット`RunInterval`のコンプライアンス構成で設定された as と同じです。

に`ConversationCollection`は、このメソッドが最後に呼び出されたときから収集されたスレッド情報が含まれています。

</div>

</div>

<span> </span>

</div>

</div>

</div>

