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

# <a name="replacing-the-xmladapter-with-a-customized-persistent-chat-server-compliance-adapter-in-lync-server-2013"></a><span data-ttu-id="4e2f3-102">Lync Server 2013 での、カスタマイズされた常設チャットサーバーのコンプライアンスアダプターを使用した Xml アダプターの置き換え</span><span class="sxs-lookup"><span data-stu-id="4e2f3-102">Replacing the XmlAdapter with a customized Persistent Chat Server Compliance adapter in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4e2f3-103">_**最終更新日:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="4e2f3-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="4e2f3-104">常設チャットサーバーと共にインストールされている XmlAdapter を使う代わりに、カスタムアダプターを作成することができます。</span><span class="sxs-lookup"><span data-stu-id="4e2f3-104">You can write a custom adapter instead of using the XmlAdapter that is installed with Persistent Chat Server.</span></span> <span data-ttu-id="4e2f3-105">記述するには、**IComplianceAdapter** インターフェイスを実装するパブリック クラスを含む .NET Framework アセンブリを提供する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4e2f3-105">To accomplish this, you must provide a .NET Framework assembly that contains a public class that implements the **IComplianceAdapter** interface.</span></span> <span data-ttu-id="4e2f3-106">このアセンブリは、常設チャットサーバープールの各サーバーの常設チャットサーバーのインストールフォルダーに配置する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4e2f3-106">You must place this assembly in the Persistent Chat Server installation folder of each server in your Persistent Chat Server pool.</span></span> <span data-ttu-id="4e2f3-107">任意のコンプライアンス サーバーからアダプターにコンプライアンス データを提供できますが、コンプライアンス サーバーからアダプターの複数のインスタンスに対して重複するコンプライアンス データを提供することはできません。</span><span class="sxs-lookup"><span data-stu-id="4e2f3-107">Any one of the Compliance servers can provide compliance data to your adapter, but the compliance servers will not provide duplicate compliance data to multiple instances of your adapter.</span></span>

<div>

## <a name="implementing-the-icomplianceadapter-interface"></a><span data-ttu-id="4e2f3-108">IComplianceAdapter インターフェイスの実装</span><span class="sxs-lookup"><span data-stu-id="4e2f3-108">Implementing the IComplianceAdapter interface</span></span>

<span data-ttu-id="4e2f3-109">インターフェイスは、名前空間`Microsoft.Rtc.Internal.Chat.Server.Compliance`の対応する .dll アセンブリで定義されます。</span><span class="sxs-lookup"><span data-stu-id="4e2f3-109">The interface is defined in the Compliance.dll assembly in the namespace `Microsoft.Rtc.Internal.Chat.Server.Compliance`.</span></span> <span data-ttu-id="4e2f3-110">このインターフェイスには、カスタム アダプターが実装する必要のある 2 つのメソッドが定義されています。</span><span class="sxs-lookup"><span data-stu-id="4e2f3-110">The interface defines two methods that your custom adapter must implement.</span></span>

    void SetConfig(AdapterConfig config)

<span data-ttu-id="4e2f3-111">常設チャットのコンプライアンスサーバーは、アダプターが最初に読み込まれたときにこのメソッドを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="4e2f3-111">The Persistent Chat Compliance server will call this method when the adapter first loads.</span></span> <span data-ttu-id="4e2f3-112">に`AdapterConfig`は、コンプライアンスアダプターに関連する常設チャットのコンプライアンス構成が含まれています。</span><span class="sxs-lookup"><span data-stu-id="4e2f3-112">The `AdapterConfig` contains the Persistent Chat compliance configuration that is relevant to the compliance adapter.</span></span>

    void Translate(ConversationCollection conversations)

<span data-ttu-id="4e2f3-113">常設チャットのコンプライアンスサーバーは、翻訳する新しいデータがある限り、定期的な間隔でこのメソッドを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="4e2f3-113">The Persistent Chat Compliance server calls this method at periodic intervals as long as there is new data to translate.</span></span> <span data-ttu-id="4e2f3-114">この時間間隔は、常設チャット`RunInterval`のコンプライアンス構成で設定された as と同じです。</span><span class="sxs-lookup"><span data-stu-id="4e2f3-114">This time interval is equal to the `RunInterval` as set in the Persistent Chat Compliance configuration.</span></span>

<span data-ttu-id="4e2f3-115">に`ConversationCollection`は、このメソッドが最後に呼び出されたときから収集されたスレッド情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="4e2f3-115">The `ConversationCollection` contains the conversation information that was collected from the last time this method was called.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

