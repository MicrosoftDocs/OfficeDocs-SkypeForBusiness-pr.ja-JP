---
title: RealWear 用 Microsoft Teams クライアントの IT 管理情報 (プレビュー)
author: MicrosoftHeidi
ms.author: heidip
manager: serdars
ms.topic: reference
ms.service: msteams
audience: admin
ms.reviewer: ''
description: RealWear 用 Microsoft Teams クライアントの IT 管理チュートリアル。
localization_priority: Priority
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
- Teams_ITAdmin_RemoteWorkers
- remotework
appliesto:
- Microsoft Teams
ms.openlocfilehash: e95440652111dbcd39b756ef942e7a974ef31de0
ms.sourcegitcommit: dc6108917392754d950cea47b92f871211bf4212
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/03/2020
ms.locfileid: "43131205"
---
# <a name="microsoft-teams-for-realwear"></a><span data-ttu-id="14ab8-103">RealWear 用 Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="14ab8-103">Microsoft Teams for RealWear</span></span>

> [!NOTE]
> <span data-ttu-id="14ab8-104">これはプレビューまたは先行リリースの機能です。</span><span class="sxs-lookup"><span data-stu-id="14ab8-104">This is a preview or early release feature.</span></span>

<span data-ttu-id="14ab8-105">この記事では、RealWear ヘッドマウント ウェアラブルを使うための Microsoft Teams クライアントについて説明します。</span><span class="sxs-lookup"><span data-stu-id="14ab8-105">This article covers the Microsoft Teams client for RealWear head-mounted wearables.</span></span> <span data-ttu-id="14ab8-106">RealWear の HMT-1 や HMT-1Z1 を使う第一線の作業員が、Teams のビデオ通話を使って遠隔地にいるエキスパートと共同作業ができるようになりました。</span><span class="sxs-lookup"><span data-stu-id="14ab8-106">FirstLine Workers using RealWear HMT-1 and HMT-1Z1 can now collaborate with a remote expert using video calling on Teams.</span></span> <span data-ttu-id="14ab8-107">RealWear 用 Teams では、音声制御のユーザー インターフェイスにより現場作業員が100% ハンズフリーの状態を維持し、これにより騒音があり危険な環境でも状況認識を確保することができます。</span><span class="sxs-lookup"><span data-stu-id="14ab8-107">Through a voice-controlled user interface, Teams for RealWear allows field workers to remain 100% hands-free while maintaining situational awareness in loud and hazardous environments.</span></span> <span data-ttu-id="14ab8-108">現場作業員が見ている光景をリアルタイムで見せることによって、問題解決までの時間を短縮し、コストのかかるダウンタイムのリスクを軽減することができます。</span><span class="sxs-lookup"><span data-stu-id="14ab8-108">By showing what they see in real-time, field workers can accelerate the time to resolve issues and reduce the risk of an expensive downtime.</span></span>

## <a name="how-to-deploy-microsoft-teams-for-realwear"></a><span data-ttu-id="14ab8-109">RealWear 用 Microsoft Teams の展開方法</span><span class="sxs-lookup"><span data-stu-id="14ab8-109">How to deploy Microsoft Teams for RealWear</span></span>

<span data-ttu-id="14ab8-110">RealWear 用 Microsoft Teams クライアントは現在、パブリック プレビュー中です。</span><span class="sxs-lookup"><span data-stu-id="14ab8-110">Microsoft Teams client for RealWear is currently in Public Preview.</span></span> <span data-ttu-id="14ab8-111">このプレビューに参加するには、次のものが必要です。</span><span class="sxs-lookup"><span data-stu-id="14ab8-111">To participate in this preview, you will need the following:</span></span>

<span data-ttu-id="14ab8-112">リリース 10.5.0 以降に更新された RealWear デバイス。</span><span class="sxs-lookup"><span data-stu-id="14ab8-112">RealWear devices updated to release 10.5.0 or above.</span></span> <span data-ttu-id="14ab8-113">詳細情報については、[こちら](https://realwear.com/knowledge-center/configure-on-release-10/wireless-update/)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="14ab8-113">More information [here](https://realwear.com/knowledge-center/configure-on-release-10/wireless-update/).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="14ab8-114">[こちら](https://www.realwear.com/solutions/microsoft-teams/#C1)で登録すると、「[RealWear の展望](https://cloud.realwear.com/)」で RealWear クライアント向けの Teams にアクセスすることができます。</span><span class="sxs-lookup"><span data-stu-id="14ab8-114">Register [here](https://www.realwear.com/solutions/microsoft-teams/#C1) for access to Teams for RealWear client in [RealWear Foresight](https://cloud.realwear.com/).</span></span>

## <a name="required-licenses"></a><span data-ttu-id="14ab8-115">必要なライセンス</span><span class="sxs-lookup"><span data-stu-id="14ab8-115">Required Licenses</span></span>

<span data-ttu-id="14ab8-116">Microsoft Teams ライセンスは、Office 365 サブスクリプションに含まれています。</span><span class="sxs-lookup"><span data-stu-id="14ab8-116">Microsoft Teams licenses are part of Office 365 subscriptions.</span></span> <span data-ttu-id="14ab8-117">RealWear 用 Teams を使用するために、追加のライセンスは必要ありません。</span><span class="sxs-lookup"><span data-stu-id="14ab8-117">No additional licensing is required to use Teams for RealWear.</span></span> <span data-ttu-id="14ab8-118">Teams の入手方法の詳細については、「 [Microsoft Teams へのアクセス方法](https://support.office.com/article/fc7f1634-abd3-4f26-a597-9df16e4ca65b)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="14ab8-118">For more information about getting Teams, check out [How do I get access to Microsoft Teams](https://support.office.com/article/fc7f1634-abd3-4f26-a597-9df16e4ca65b).</span></span>

## <a name="managing-realwear-devices"></a><span data-ttu-id="14ab8-119">RealWear デバイスを管理する</span><span class="sxs-lookup"><span data-stu-id="14ab8-119">Managing RealWear devices</span></span>

### <a name="microsoft-endpoint-manager"></a><span data-ttu-id="14ab8-120">Microsoft エンドポイント マネージャー</span><span class="sxs-lookup"><span data-stu-id="14ab8-120">Microsoft Endpoint Manager</span></span>

<span data-ttu-id="14ab8-121">Android デバイス管理者モードを使用して、RealWear デバイスを管理することができます。</span><span class="sxs-lookup"><span data-stu-id="14ab8-121">RealWear devices can be managed using Android Device Administrator mode.</span></span> <span data-ttu-id="14ab8-122">Android Enterprise による管理のサポートには制限があり、現在、デバイスでは Google モバイル サービス (GMS) は利用できません。</span><span class="sxs-lookup"><span data-stu-id="14ab8-122">Support for management via Android Enterprise is limited, as the devices currently don't have Google Mobile Services (GMS) available.</span></span>

- <span data-ttu-id="14ab8-123">Microsoft エンドポイント マネージャーによる RealWear デバイス管理の詳細については、「[Intune での Android デバイス管理者の登録](https://docs.microsoft.com/mem/intune/enrollment/android-enroll-device-administrator)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="14ab8-123">To learn more about managing RealWear devices on Microsoft Endpoint Manager, see [Android device administrator enrollment in Intune](https://docs.microsoft.com/mem/intune/enrollment/android-enroll-device-administrator).</span></span>
- <span data-ttu-id="14ab8-124">ポリシーの詳細については、「[Google モバイル サービスを使用していない環境で Intune を使用する方法](https://docs.microsoft.com/mem/intune/apps/manage-without-gms)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="14ab8-124">For more details on policies, see [How to use Intune in environments without Google Mobile Services](https://docs.microsoft.com/mem/intune/apps/manage-without-gms).</span></span>

### <a name="third-party-enterprise-mobility-managers-emms"></a><span data-ttu-id="14ab8-125">サードパーティ製 Enterprise Mobility マネージャー (EMM)</span><span class="sxs-lookup"><span data-stu-id="14ab8-125">Third-party Enterprise Mobility Managers (EMMs)</span></span>

<span data-ttu-id="14ab8-126">サードパーティ製の EMM についてのガイダンスは、「[サポートされている Enterprise Mobility 管理プロバイダー](https://www.realwear.com/knowledge-center/configure-on-release-10/remote-from-a-web-browser/emm/)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="14ab8-126">For guidance on third-party EMMs, see [Supported Enterprise Mobility Management Providers](https://www.realwear.com/knowledge-center/configure-on-release-10/remote-from-a-web-browser/emm/).</span></span>

## <a name="end-user-content"></a><span data-ttu-id="14ab8-127">エンドユーザーのコンテンツ</span><span class="sxs-lookup"><span data-stu-id="14ab8-127">End-user content</span></span>

<span data-ttu-id="14ab8-128">エンドユーザーの観点からのさらに詳しい情報については、「[Microsoft Teams を RealWear に使用する](https://support.office.com/article/using-microsoft-teams-for-realwear-af20d232-d18c-476f-8031-843a4edccd5f)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="14ab8-128">For further reading on this from an end-user perspective, please check out [Using Microsoft Teams for RealWear](https://support.office.com/article/using-microsoft-teams-for-realwear-af20d232-d18c-476f-8031-843a4edccd5f).</span></span>
