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
ms.openlocfilehash: 222cb12e38061c81a860092f90bf42d5412fdb63
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51092285"
---
# <a name="microsoft-teams-for-realwear"></a><span data-ttu-id="aee88-103">RealWear 用 Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="aee88-103">Microsoft Teams for RealWear</span></span>

<span data-ttu-id="aee88-104">この記事では、RealWear ヘッドマウント ウェアラブルを使うための Microsoft Teams クライアントについて説明します。</span><span class="sxs-lookup"><span data-stu-id="aee88-104">This article covers the Microsoft Teams client for RealWear head-mounted wearables.</span></span> <span data-ttu-id="aee88-105">RealWear の HMT-1 や HMT-1Z1 を使う現場担当者が、Teams のビデオ通話を使って遠隔地にいるエキスパートと共同作業ができるようになりました。</span><span class="sxs-lookup"><span data-stu-id="aee88-105">Frontline Workers using RealWear HMT-1 and HMT-1Z1 can now collaborate with a remote expert using video calling on Teams.</span></span> <span data-ttu-id="aee88-106">RealWear 用 Teams では、音声制御のユーザー インターフェイスにより現場作業員が100% ハンズフリーの状態を維持し、これにより騒音があり危険な環境でも状況認識を確保することができます。</span><span class="sxs-lookup"><span data-stu-id="aee88-106">Through a voice-controlled user interface, Teams for RealWear allows field workers to remain 100% hands-free while maintaining situational awareness in loud and hazardous environments.</span></span> <span data-ttu-id="aee88-107">現場作業員が見ている光景をリアルタイムで見せることによって、問題解決までの時間を短縮し、コストのかかるダウンタイムのリスクを軽減することができます。</span><span class="sxs-lookup"><span data-stu-id="aee88-107">By showing what they see in real-time, field workers can accelerate the time to resolve issues and reduce the risk of an expensive downtime.</span></span>

## <a name="how-to-deploy-microsoft-teams-for-realwear"></a><span data-ttu-id="aee88-108">RealWear 用 Microsoft Teams の展開方法</span><span class="sxs-lookup"><span data-stu-id="aee88-108">How to deploy Microsoft Teams for RealWear</span></span>

- <span data-ttu-id="aee88-109">リリース 11.2 以降に更新された RealWear デバイス。</span><span class="sxs-lookup"><span data-stu-id="aee88-109">RealWear devices updated to release 11.2 or above.</span></span> <span data-ttu-id="aee88-110">詳細情報については、[こちら](https://realwear.com/knowledge-center/configure-on-release-10/wireless-update/) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="aee88-110">More information [here](https://realwear.com/knowledge-center/configure-on-release-10/wireless-update/).</span></span>
- <span data-ttu-id="aee88-111">Realwear 用 Microsoft Teams クライアントを配布するための [RealWear Foresight](https://cloud.realwear.com/) へのアクセス。</span><span class="sxs-lookup"><span data-stu-id="aee88-111">Access to [RealWear Foresight](https://cloud.realwear.com/) for distributing the Microsoft Teams client for Realwear.</span></span>

## <a name="required-licenses"></a><span data-ttu-id="aee88-112">必要なライセンス</span><span class="sxs-lookup"><span data-stu-id="aee88-112">Required Licenses</span></span>

<span data-ttu-id="aee88-113">Microsoft Teams ライセンスは、Microsoft 365 サブスクリプションおよび Office 365 サブスクリプションに含まれています。</span><span class="sxs-lookup"><span data-stu-id="aee88-113">Microsoft Teams licenses are part of Microsoft 365 and Office 365 subscriptions.</span></span> <span data-ttu-id="aee88-114">RealWear 用 Teams を使用するために、追加のライセンスは必要ありません。</span><span class="sxs-lookup"><span data-stu-id="aee88-114">No additional licensing is required to use Teams for RealWear.</span></span> <span data-ttu-id="aee88-115">Teams の入手方法の詳細については、「 [Microsoft Teams へのアクセス方法](https://support.office.com/article/fc7f1634-abd3-4f26-a597-9df16e4ca65b)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="aee88-115">For more information about getting Teams, check out [How do I get access to Microsoft Teams](https://support.office.com/article/fc7f1634-abd3-4f26-a597-9df16e4ca65b).</span></span>

## <a name="managing-realwear-devices"></a><span data-ttu-id="aee88-116">RealWear デバイスを管理する</span><span class="sxs-lookup"><span data-stu-id="aee88-116">Managing RealWear devices</span></span>

### <a name="microsoft-endpoint-manager"></a><span data-ttu-id="aee88-117">Microsoft エンドポイント マネージャー</span><span class="sxs-lookup"><span data-stu-id="aee88-117">Microsoft Endpoint Manager</span></span>

<span data-ttu-id="aee88-118">Android デバイス管理者モードを使用して、RealWear デバイスを管理することができます。</span><span class="sxs-lookup"><span data-stu-id="aee88-118">RealWear devices can be managed using Android Device Administrator mode.</span></span> <span data-ttu-id="aee88-119">Android Enterprise による管理のサポートには制限があり、現在、デバイスでは Google モバイル サービス (GMS) は利用できません。</span><span class="sxs-lookup"><span data-stu-id="aee88-119">Support for management via Android Enterprise is limited, as the devices currently don't have Google Mobile Services (GMS) available.</span></span>

- <span data-ttu-id="aee88-120">Microsoft エンドポイント マネージャーによる RealWear デバイス管理の詳細については、「[Intune での Android デバイス管理者の登録](/mem/intune/enrollment/android-enroll-device-administrator)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="aee88-120">To learn more about managing RealWear devices on Microsoft Endpoint Manager, see [Android device administrator enrollment in Intune](/mem/intune/enrollment/android-enroll-device-administrator).</span></span>
- <span data-ttu-id="aee88-121">ポリシーの詳細については、「[Google モバイル サービスを使用していない環境で Intune を使用する方法](/mem/intune/apps/manage-without-gms)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="aee88-121">For more details on policies, see [How to use Intune in environments without Google Mobile Services](/mem/intune/apps/manage-without-gms).</span></span>

### <a name="third-party-enterprise-mobility-managers-emms"></a><span data-ttu-id="aee88-122">サードパーティ製 Enterprise Mobility マネージャー (EMM)</span><span class="sxs-lookup"><span data-stu-id="aee88-122">Third-party Enterprise Mobility Managers (EMMs)</span></span>

<span data-ttu-id="aee88-123">サードパーティ製の EMM についてのガイダンスは、「[サポートされている Enterprise Mobility 管理プロバイダー](https://www.realwear.com/knowledge-center/configure-on-release-10/remote-from-a-web-browser/emm/)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="aee88-123">For guidance on third-party EMMs, see [Supported Enterprise Mobility Management Providers](https://www.realwear.com/knowledge-center/configure-on-release-10/remote-from-a-web-browser/emm/).</span></span>

## <a name="end-user-content"></a><span data-ttu-id="aee88-124">エンドユーザーのコンテンツ</span><span class="sxs-lookup"><span data-stu-id="aee88-124">End-user content</span></span>

<span data-ttu-id="aee88-125">エンドユーザーの観点からのさらに詳しい情報については、「[Microsoft Teams を RealWear に使用する](https://support.office.com/article/using-microsoft-teams-for-realwear-af20d232-d18c-476f-8031-843a4edccd5f)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="aee88-125">For further reading on this from an end-user perspective, please check out [Using Microsoft Teams for RealWear](https://support.office.com/article/using-microsoft-teams-for-realwear-af20d232-d18c-476f-8031-843a4edccd5f).</span></span>