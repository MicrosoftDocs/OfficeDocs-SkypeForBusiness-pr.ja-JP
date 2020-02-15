---
title: 'Lync Server 2013: Lync for Android の要件'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Lync for Android requirements
ms:assetid: 4ff53e03-0c1f-4a2b-9cec-1131c2a48563
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh690980(v=OCS.15)
ms:contentKeyID: 53312965
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c89439f46c98fd1f00d7cb95eb4a910b26971be0
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42030901"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="lync-for-android-requirements-in-lync-server-2013"></a><span data-ttu-id="d7125-102">Lync Server 2013 での lync for Android の要件</span><span class="sxs-lookup"><span data-stu-id="d7125-102">Lync for Android requirements in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d7125-103">_**トピックの最終更新日:** 2014-04-24_</span><span class="sxs-lookup"><span data-stu-id="d7125-103">_**Topic Last Modified:** 2014-04-24_</span></span>

<span data-ttu-id="d7125-104">Microsoft Lync 2013 Microsoft Lync 2013 for Android は、Android デバイスから接続している組織内のユーザーに、インスタントメッセージング (IM)、拡張プレゼンス、および Lync 会議参加機能を提供します。</span><span class="sxs-lookup"><span data-stu-id="d7125-104">Microsoft Lync 2013 Microsoft Lync 2013 for Android provides instant messaging (IM), enhanced presence, and Lync meeting join capabilities for users in your organization who are connecting from an Android device.</span></span> <span data-ttu-id="d7125-105">このトピックでは、前提条件、技術要件、必要なコンポーネントを含む、Lync 2013 for Android の考慮事項について説明します。</span><span class="sxs-lookup"><span data-stu-id="d7125-105">This topic describes considerations for Lync 2013 for Android, including prerequisites, technical requirements, and required components.</span></span>

<div>

## <a name="lync-for-android-prerequisite"></a><span data-ttu-id="d7125-106">Lync for Android の前提条件</span><span class="sxs-lookup"><span data-stu-id="d7125-106">Lync for Android Prerequisite</span></span>

<span data-ttu-id="d7125-107">Android 用 Lync 2013 をサポートするには、Android デバイスは次の要件を満たしている必要があります。</span><span class="sxs-lookup"><span data-stu-id="d7125-107">To support Lync 2013 for Android, the Android device must meet the following requirements:</span></span>

  - <span data-ttu-id="d7125-108">Android デバイスは、Android 4.0 またはそれ以降の電話機またはタブレット指向のオペレーティングシステムを実行している必要があります (Tegra2 チップを除く)。</span><span class="sxs-lookup"><span data-stu-id="d7125-108">The Android device must be running Android 4.0 or a later phone- or tablet-oriented operating system, including tablets, except those with the Tegra2 chip.</span></span>

  - <span data-ttu-id="d7125-109">デバイスには、1.2 GHz のデュアルコアまたはそれ以上の CPU が搭載されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="d7125-109">The device must have a 1.2 GHz dual core or higher CPU.</span></span>

  - <span data-ttu-id="d7125-110">デバイスカメラ (フロント/リア) 解像度は VGA 以上である必要があります。</span><span class="sxs-lookup"><span data-stu-id="d7125-110">The device camera (front/rear) resolution should be VGA or higher.</span></span>

  - <span data-ttu-id="d7125-111">その他のハードウェア要件は、Android 4.0 の互換性の定義ドキュメントに合わせる必要があります。</span><span class="sxs-lookup"><span data-stu-id="d7125-111">Other hardware requirements should be aligned with Android 4.0 Compatibility Definition Document.</span></span>

</div>

<div>

## <a name="other-technical-considerations"></a><span data-ttu-id="d7125-112">その他の技術的考慮事項</span><span class="sxs-lookup"><span data-stu-id="d7125-112">Other Technical Considerations</span></span>

<span data-ttu-id="d7125-113">Android デバイスプラットフォームでは、Lync アプリケーションをバックグラウンドで実行できます。</span><span class="sxs-lookup"><span data-stu-id="d7125-113">On the Android device platform, the Lync application can run in the background.</span></span> <span data-ttu-id="d7125-114">そのため、他のモバイルデバイスプラットフォームとは異なり、Android デバイスでプッシュ通知が必要になることはありません。</span><span class="sxs-lookup"><span data-stu-id="d7125-114">Therefore, unlike other mobile device platforms, push notifications are not required for Android devices.</span></span> <span data-ttu-id="d7125-115">Android デバイスで Lync アプリケーションを終了する唯一の方法は、Lync から明示的にサインアウトすることです。</span><span class="sxs-lookup"><span data-stu-id="d7125-115">The only way to exit the Lync application on an Android device is to explicitly sign out of Lync.</span></span> <span data-ttu-id="d7125-116">このバージョンの Lync アプリケーションは、Tegra 2 チップセットのデバイスではサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="d7125-116">This version of the Lync application is not supported on devices with Tegra 2 chipsets.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

