---
title: 'Lync Server 2013: カスタマイズされた常設チャットサーバーコンプライアンスアダプターを使用して XmlAdapter を置き換える'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Replacing the XmlAdapter with a customized Persistent Chat Server Compliance adapter
ms:assetid: 2cb70db2-663f-40a6-abcf-89ea7d4a8b65
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ680106(v=OCS.15)
ms:contentKeyID: 49558152
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6e9cd9f2e950e835a113f64795022753e44e3ff5
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2020
ms.locfileid: "42214953"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="replacing-the-xmladapter-with-a-customized-persistent-chat-server-compliance-adapter-in-lync-server-2013"></a>Lync Server 2013 で、カスタマイズされた常設チャットサーバーコンプライアンスアダプターに XmlAdapter を置き換える

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-11-01_

常設チャットサーバーと共にインストールされる XmlAdapter を使用する代わりに、カスタムアダプターを作成することができます。 カスタム アダプターを記述するには、**IComplianceAdapter** インターフェイスを実装するパブリック クラスを含む .NET Framework アセンブリを提供する必要があります。 このアセンブリは、常設チャットサーバープールの各サーバーの常設チャットサーバーのインストールフォルダーに配置する必要があります。 任意のコンプライアンス サーバーからアダプターにコンプライアンス データを提供できますが、コンプライアンス サーバーからアダプターの複数のインスタンスに対して重複するコンプライアンス データを提供することはできません。

<div>

## <a name="implementing-the-icomplianceadapter-interface"></a>IComplianceAdapter インターフェイスの実装

このインターフェイスは、名前空間`Microsoft.Rtc.Internal.Chat.Server.Compliance`内の対応する .dll アセンブリに定義されています。 このインターフェイスには、カスタム アダプターが実装する必要のある 2 つのメソッドが定義されています。

    void SetConfig(AdapterConfig config)

常設チャットコンプライアンスサーバーは、アダプターが最初に読み込まれたときにこのメソッドを呼び出します。 に`AdapterConfig`は、コンプライアンスアダプターに関連する常設チャットのコンプライアンス構成が含まれています。

    void Translate(ConversationCollection conversations)

常設チャットコンプライアンスサーバーは、翻訳する新しいデータがある限り、定期的な間隔でこのメソッドを呼び出します。 この時間間隔は、常設チャット`RunInterval`のコンプライアンス構成で設定されたと同じです。

に`ConversationCollection`は、このメソッドが最後に呼び出されたときに収集された会話情報が含まれています。

</div>

</div>

<span> </span>

</div>

</div>

</div>

