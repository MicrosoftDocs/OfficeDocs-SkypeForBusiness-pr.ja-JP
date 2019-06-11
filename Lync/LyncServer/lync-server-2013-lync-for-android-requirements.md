---
title: 'Lync Server 2013: Lync for Android の要件'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Lync for Android requirements
ms:assetid: 4ff53e03-0c1f-4a2b-9cec-1131c2a48563
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh690980(v=OCS.15)
ms:contentKeyID: 53312965
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fb4c7ce56fb65b9f5998af90bfe63ab6eed5d28c
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34832928"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="lync-for-android-requirements-in-lync-server-2013"></a><span data-ttu-id="efeba-102">Lync for Android の要件 Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="efeba-102">Lync for Android requirements in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="efeba-103">_**最終更新日:** 2014-04-24_</span><span class="sxs-lookup"><span data-stu-id="efeba-103">_**Topic Last Modified:** 2014-04-24_</span></span>

<span data-ttu-id="efeba-104">Microsoft Lync 2013 Microsoft Lync 2013 for Android では、Android デバイスから接続している組織内のユーザーに対してインスタントメッセージング (IM)、拡張プレゼンス、および Lync 会議参加機能が提供されます。</span><span class="sxs-lookup"><span data-stu-id="efeba-104">Microsoft Lync 2013 Microsoft Lync 2013 for Android provides instant messaging (IM), enhanced presence, and Lync meeting join capabilities for users in your organization who are connecting from an Android device.</span></span> <span data-ttu-id="efeba-105">このトピックでは、前提条件、技術要件、必須コンポーネントなど、Lync 2013 for Android の考慮事項について説明します。</span><span class="sxs-lookup"><span data-stu-id="efeba-105">This topic describes considerations for Lync 2013 for Android, including prerequisites, technical requirements, and required components.</span></span>

<div>

## <a name="lync-for-android-prerequisite"></a><span data-ttu-id="efeba-106">Lync for Android の前提条件</span><span class="sxs-lookup"><span data-stu-id="efeba-106">Lync for Android Prerequisite</span></span>

<span data-ttu-id="efeba-107">Android 用の Lync 2013 をサポートするには、Android デバイスは次の要件を満たしている必要があります。</span><span class="sxs-lookup"><span data-stu-id="efeba-107">To support Lync 2013 for Android, the Android device must meet the following requirements:</span></span>

  - <span data-ttu-id="efeba-108">Android デバイスでは、Android 4.0 以降の電話またはタブレット搭載のオペレーティングシステムが実行されている必要があります (Tegra2 チップを除く)。</span><span class="sxs-lookup"><span data-stu-id="efeba-108">The Android device must be running Android 4.0 or a later phone- or tablet-oriented operating system, including tablets, except those with the Tegra2 chip.</span></span>

  - <span data-ttu-id="efeba-109">デバイスには、1.2 GHz のデュアルコア以上の CPU が搭載されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="efeba-109">The device must have a 1.2 GHz dual core or higher CPU.</span></span>

  - <span data-ttu-id="efeba-110">デバイスカメラ (フロント/リア) 解像度は VGA 以上である必要があります。</span><span class="sxs-lookup"><span data-stu-id="efeba-110">The device camera (front/rear) resolution should be VGA or higher.</span></span>

  - <span data-ttu-id="efeba-111">その他のハードウェア要件は、Android 4.0 互換性定義ドキュメントに合わせる必要があります。</span><span class="sxs-lookup"><span data-stu-id="efeba-111">Other hardware requirements should be aligned with Android 4.0 Compatibility Definition Document.</span></span>

</div>

<div>

## <a name="other-technical-considerations"></a><span data-ttu-id="efeba-112">その他の技術的な考慮事項</span><span class="sxs-lookup"><span data-stu-id="efeba-112">Other Technical Considerations</span></span>

<span data-ttu-id="efeba-113">Android デバイスプラットフォームでは、Lync アプリケーションをバックグラウンドで実行できます。</span><span class="sxs-lookup"><span data-stu-id="efeba-113">On the Android device platform, the Lync application can run in the background.</span></span> <span data-ttu-id="efeba-114">そのため、他のモバイルデバイスプラットフォームとは異なり、プッシュ通知は Android デバイスでは必要ありません。</span><span class="sxs-lookup"><span data-stu-id="efeba-114">Therefore, unlike other mobile device platforms, push notifications are not required for Android devices.</span></span> <span data-ttu-id="efeba-115">Android デバイスで Lync アプリケーションを終了するには、Lync から明示的にサインアウトする方法しかありません。</span><span class="sxs-lookup"><span data-stu-id="efeba-115">The only way to exit the Lync application on an Android device is to explicitly sign out of Lync.</span></span> <span data-ttu-id="efeba-116">このバージョンの Lync アプリケーションは、Tegra 2 チップセットを搭載したデバイスではサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="efeba-116">This version of the Lync application is not supported on devices with Tegra 2 chipsets.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

