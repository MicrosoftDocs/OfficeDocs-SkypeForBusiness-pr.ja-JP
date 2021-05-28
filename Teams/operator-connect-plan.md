---
title: 演算子Connect
author: cazawideh
ms.author: czawideh
manager: serdars
ms.date: 04/12/2021
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-voice
- m365initiative-voice
ms.reviewer: crowe
search.appverid: MET150
f1.keywords:
- NOCSH
- ms.teamsadmincenter.directrouting.overview
description: デプロイの要件や計画などConnectオペレーター の詳細を確認します。
ms.custom:
- seo-marvel-apr2020
- seo-marvel-jun2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 088b36f546cebe67e10d840075e601e96a6df6e2
ms.sourcegitcommit: 39d26edd43b6066d5a6dee2a5ad1354a1e560a0d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/27/2021
ms.locfileid: "52694542"
---
# <a name="plan-for-operator-connect"></a><span data-ttu-id="e77e4-103">オペレーター サービスのConnect</span><span class="sxs-lookup"><span data-stu-id="e77e4-103">Plan for Operator Connect</span></span>

>[!NOTE]
><span data-ttu-id="e77e4-104">オペレーター Connectは、現在パブリック プレビューでのみ **使用できます**。</span><span class="sxs-lookup"><span data-stu-id="e77e4-104">Operator Connect is currently available only in **public preview**.</span></span> <span data-ttu-id="e77e4-105">パブリック プレビューでは、今後の機能をテストし、フィードバックを提供できます。</span><span class="sxs-lookup"><span data-stu-id="e77e4-105">Public preview allows you to test upcoming features and provide feedback.</span></span> <span data-ttu-id="e77e4-106">パブリック プレビューに含まれる機能は、完全ではなく、変更される可能性があります。また、Office 365 Government Cloud ではサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="e77e4-106">Features included in public preview may not be complete, may undergo changes, and are not supported in Office 365 Government Cloud.</span></span>

<span data-ttu-id="e77e4-107">オペレーター Connectは、PSTN (公衆交換電話網) と通信ネットワークとの間の接続を提供Teamsオプション電話システム。</span><span class="sxs-lookup"><span data-stu-id="e77e4-107">Operator Connect is another option for providing Public Switched Telephone Network (PSTN) connectivity with Teams and Phone System.</span></span>  

<span data-ttu-id="e77e4-108">この記事では、メリットと要件について説明し、オペレーター プログラムに参加しているオペレーター Connectします。</span><span class="sxs-lookup"><span data-stu-id="e77e4-108">This article describes benefits and requirements, and lists the operators participating in the Operator Connect Program.</span></span>  <span data-ttu-id="e77e4-109">組織に適切なソリューションConnect Operator Connect決定した場合は、この記事を読んだ後、「Configure Operator Connect 」を[参照してください](operator-connect-configure.md)。</span><span class="sxs-lookup"><span data-stu-id="e77e4-109">If you decide Operator Connect is the right solution for your organization, after reading this article, see [Configure Operator Connect](operator-connect-configure.md).</span></span>  

## <a name="benefits"></a><span data-ttu-id="e77e4-110">利点</span><span class="sxs-lookup"><span data-stu-id="e77e4-110">Benefits</span></span>

<span data-ttu-id="e77e4-111">オペレーター Connectを使用すると、既存のオペレーターが Microsoft Operator Connect プログラムに参加している場合、PSTN 通話を Teams に持ち込むサービスを管理できます。</span><span class="sxs-lookup"><span data-stu-id="e77e4-111">With Operator Connect, if your existing operator is a participant in the Microsoft Operator Connect program, they can manage the service for bringing PSTN calling to Teams.</span></span> <span data-ttu-id="e77e4-112">Operator Connect プログラムには、次の利点があります。</span><span class="sxs-lookup"><span data-stu-id="e77e4-112">The Operator Connect program provides the following benefits:</span></span>

- <span data-ttu-id="e77e4-113">**既存のコントラクトを活用するか、新しい演算子を見つける。**</span><span class="sxs-lookup"><span data-stu-id="e77e4-113">**Leverage existing contracts, or find a new operator.**</span></span> <span data-ttu-id="e77e4-114">希望するオペレーターと契約を維持するか、ビジネス ニーズに合わせて、参加しているオペレーターの選択から新しいオペレーターを選択します。</span><span class="sxs-lookup"><span data-stu-id="e77e4-114">You keep your preferred operator and contracts, or choose a new one from a selection of participating operators to meet your business needs.</span></span>

- <span data-ttu-id="e77e4-115">**オペレーターが管理するインフラストラクチャ。**</span><span class="sxs-lookup"><span data-stu-id="e77e4-115">**Operator-managed infrastructure.**</span></span> <span data-ttu-id="e77e4-116">オペレーターが PSTN 通話サービスとセッション ボーダー コントローラー (SBC) を管理し、ハードウェアの購入と管理を節約できます。</span><span class="sxs-lookup"><span data-stu-id="e77e4-116">Your operator manages the PSTN calling services and Session Border Controllers (SBCs), allowing you to save on hardware purchase and management.</span></span>

- <span data-ttu-id="e77e4-117">**デプロイの高速化、簡単。**</span><span class="sxs-lookup"><span data-stu-id="e77e4-117">**Faster, easier deployment.**</span></span> <span data-ttu-id="e77e4-118">オペレーターにすばやく接続し、電話番号をユーザーに割り当て、管理センター Teamsできます。</span><span class="sxs-lookup"><span data-stu-id="e77e4-118">You can quickly connect to your operator and assign phone numbers to users -– all from the Teams Admin Center.</span></span>

- <span data-ttu-id="e77e4-119">**サポートと信頼性の強化。**</span><span class="sxs-lookup"><span data-stu-id="e77e4-119">**Enhanced support and reliability.**</span></span> <span data-ttu-id="e77e4-120">オペレーターは、サポート サービスを向上させるためにテクニカル サポートと共有サービス レベル アグリーメントを提供しますが、Azure を利用した直接ピアリングでは、信頼性を向上させるために 1 対 1 のネットワーク接続が作成されます。</span><span class="sxs-lookup"><span data-stu-id="e77e4-120">Operators provide technical support and shared service level agreements to improve support service, while direct peering powered by Azure creates a one-to-one network connection for enhanced reliability.</span></span>

## <a name="requirements"></a><span data-ttu-id="e77e4-121">要件</span><span class="sxs-lookup"><span data-stu-id="e77e4-121">Requirements</span></span>

 <span data-ttu-id="e77e4-122">オペレーター Connectは、次の場合に組織に適切なソリューションになる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="e77e4-122">Operator Connect might be the right solution for your organization if:</span></span>

- <span data-ttu-id="e77e4-123">Microsoft 通話プランは、地理的な場所では利用できません。</span><span class="sxs-lookup"><span data-stu-id="e77e4-123">Microsoft Calling Plan isn't available in your geographic location.</span></span>
- <span data-ttu-id="e77e4-124">お好みのオペレーターは、Microsoft Operator Connectです。</span><span class="sxs-lookup"><span data-stu-id="e77e4-124">Your preferred operator is a participant in the Microsoft Operator Connect program.</span></span>
- <span data-ttu-id="e77e4-125">新しい演算子を検索して、Teams で呼び出しを有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="e77e4-125">You want to find a new operator to enable calling in Teams.</span></span>

<span data-ttu-id="e77e4-126">オペレーター アカウントで電話番号の割り当てを有効Connect、ユーザーが次の条件を持つ必要があります。</span><span class="sxs-lookup"><span data-stu-id="e77e4-126">To enable phone number assignments with Operator Connect, make sure your users are:</span></span>

- <span data-ttu-id="e77e4-127">Teams 電話ライセンスされています。</span><span class="sxs-lookup"><span data-stu-id="e77e4-127">Teams Phone licensed.</span></span> <span data-ttu-id="e77e4-128">詳細については、「What [is 電話システム?」](what-is-phone-system-in-office-365.md)および「ユーザーに Teams アドオン ライセンスを割[り当てる」を参照してください](teams-add-on-licensing/assign-teams-add-on-licenses.md)。</span><span class="sxs-lookup"><span data-stu-id="e77e4-128">To learn more, see [What is Phone System?](what-is-phone-system-in-office-365.md) and [Assign Teams add-on licenses to users](teams-add-on-licensing/assign-teams-add-on-licenses.md).</span></span>
- <span data-ttu-id="e77e4-129">TeamsOnly モード。</span><span class="sxs-lookup"><span data-stu-id="e77e4-129">In TeamsOnly mode.</span></span> <span data-ttu-id="e77e4-130">詳細については、「共存と相互[運用性Microsoft TeamsとSkype for Businessを理解する」を参照してください](teams-and-skypeforbusiness-coexistence-and-interoperability.md)。</span><span class="sxs-lookup"><span data-stu-id="e77e4-130">To learn more, see [Understand Microsoft Teams and Skype for Business coexistence and interoperability](teams-and-skypeforbusiness-coexistence-and-interoperability.md).</span></span>

## <a name="available-operators"></a><span data-ttu-id="e77e4-131">使用可能な演算子</span><span class="sxs-lookup"><span data-stu-id="e77e4-131">Available Operators</span></span>

<span data-ttu-id="e77e4-132">次の演算子は、Microsoft Operator Connectプログラムの参加者です。</span><span class="sxs-lookup"><span data-stu-id="e77e4-132">The following operators are participants in the Microsoft Operator Connect program:</span></span>

| <span data-ttu-id="e77e4-133">オペレーター</span><span class="sxs-lookup"><span data-stu-id="e77e4-133">Operator</span></span> | <span data-ttu-id="e77e4-134">機能</span><span class="sxs-lookup"><span data-stu-id="e77e4-134">Capability</span></span> | <span data-ttu-id="e77e4-135">国の対象範囲</span><span class="sxs-lookup"><span data-stu-id="e77e4-135">Country coverage</span></span> |
| --- | --- | --- |
| `BT`  | <span data-ttu-id="e77e4-136">通話</span><span class="sxs-lookup"><span data-stu-id="e77e4-136">Calling</span></span> | <span data-ttu-id="e77e4-137">ベルギー、デンマーク、フィンランド、フランス、ドイツ、アイルランド、イタリア、ルクセンブルク、オランダ、ノルウェー、ポーランド、南アフリカ、スペイン、スウェーデン、スイス、英国</span><span class="sxs-lookup"><span data-stu-id="e77e4-137">Belgium, Denmark, Finland, France, Germany, Ireland, Italy, Luxembourg, Netherlands, Norway, Poland, South Africa, Spain, Sweden, Switzerland, United Kingdom</span></span> |
| `Intrado` | <span data-ttu-id="e77e4-138">通話</span><span class="sxs-lookup"><span data-stu-id="e77e4-138">Calling</span></span> | <span data-ttu-id="e77e4-139">ベルギー、カナダ、デンマーク、フランス、ドイツ、アイルランド、ルクセンブルク、オランダ、スペイン、スウェーデン、英国、米国</span><span class="sxs-lookup"><span data-stu-id="e77e4-139">Belgium, Canada, Denmark, France, Germany, Ireland, Luxembourg, Netherlands, Spain, Sweden, United Kingdom, United States</span></span>  |
| `NTT`  | <span data-ttu-id="e77e4-140">通話</span><span class="sxs-lookup"><span data-stu-id="e77e4-140">Calling</span></span> | <span data-ttu-id="e77e4-141">オーストリア、ベルギー、ブラジル、カナダ、チェコ、デンマーク、フィンランド、フランス、ドイツ、アイルランド、イタリア、ルクセンブルク、メキシコ、オランダ、ノルウェー、ポーランド、ポルトガル、プエルトリコ、ルーマニア、南アフリカ、スペイン、スウェーデン、スイス、英国、米国</span><span class="sxs-lookup"><span data-stu-id="e77e4-141">Austria, Belgium, Brazil, Canada, Czechia, Denmark, Finland,  France, Germany, Ireland, Italy, Luxembourg, Mexico, Netherlands, Norway, Poland, Portugal, Puerto Rico, Romania, South Africa, Spain, Sweden, Switzerland, United Kingdom, United States</span></span> |
| `NuWave` | <span data-ttu-id="e77e4-142">通話</span><span class="sxs-lookup"><span data-stu-id="e77e4-142">Calling</span></span> | <span data-ttu-id="e77e4-143">オーストリア、ベルギー、カナダ、デンマーク、フランス、ドイツ、アイルランド、イタリア、オランダ、ポルトガル、スペイン、スウェーデン、スイス、英国、米国</span><span class="sxs-lookup"><span data-stu-id="e77e4-143">Austria, Belgium, Canada, Denmark, France, Germany, Ireland, Italy, Netherlands, Portugal, Spain, Sweden, Switzerland, United Kingdom, United States</span></span>   |
| `Orange Business Services` | <span data-ttu-id="e77e4-144">通話</span><span class="sxs-lookup"><span data-stu-id="e77e4-144">Calling</span></span> | <span data-ttu-id="e77e4-145">オーストリア、ベルギー、チェコ、デンマーク、フィンランド、フランス、ギアナ、ドイツ、グアドループ、アイルランド、イタリア、ルクセンブルク、マルチニーク、マヨット、オランダ、ノルウェー、ポーランド、ポルトガル、レウニオン、サン・バルテレンティ、サン・マルタン、スペイン、スバルバルド、スウェーデン、スイス、英国</span><span class="sxs-lookup"><span data-stu-id="e77e4-145">Austria, Belgium, Czechia, Denmark, Finland, France, French Guiana, Germany, Guadeloupe, Ireland, Italy, Luxembourg, Martinique, Mayotte, Netherlands, Norway, Poland, Portugal, Réunion, Saint Barthélemy, Saint Martin, Spain, Svalbard, Sweden, Switzerland, United Kingdom</span></span>  |
| `Pure IP` | <span data-ttu-id="e77e4-146">通話</span><span class="sxs-lookup"><span data-stu-id="e77e4-146">Calling</span></span> | <span data-ttu-id="e77e4-147">オーストラリア、オーストリア、ベルギー、ブラジル、ブルガリア、カナダ、チリ、コロンビア、クロアチア、キプロス、チェコ、デンマーク、フィンランド、フランス、ドイツ、ギリシャ、香港ドル、ギリシャ、アイルランド、イタリア、日本、リトアニア、ルクセンブルク、マレーシア、メキシコ、オランダ、ニュージーランド、ノルウェー、ブラジル、ポルトガル、プエルトリコ、ルーマニア、シンガポール、スロバキア、スロベニア、南アフリカ、スペイン、スウェーデン、スイス、英国、米国</span><span class="sxs-lookup"><span data-stu-id="e77e4-147">Australia, Austria, Belgium, Brazil, Bulgaria, Canada, Chile, Colombia, Croatia, Cyprus, Czechia, Denmark, Finland, France, Germany, Greece, Hong Kong S.A.R., Ireland, Italy, Japan, Lithuania, Luxembourg, Malaysia, Mexico, Netherlands, New Zealand, Norway, Panama, Poland, Portugal, Puerto Rico, Romania, Singapore, Slovakia, Slovenia, South Africa, Spain, Sweden, Switzerland, United Kingdom, United States</span></span>  |
| `Rogers Business` | <span data-ttu-id="e77e4-148">通話</span><span class="sxs-lookup"><span data-stu-id="e77e4-148">Calling</span></span> | <span data-ttu-id="e77e4-149">カナダ</span><span class="sxs-lookup"><span data-stu-id="e77e4-149">Canada</span></span>  |
| `TATA Communications` | <span data-ttu-id="e77e4-150">通話</span><span class="sxs-lookup"><span data-stu-id="e77e4-150">Calling</span></span> | <span data-ttu-id="e77e4-151">オーストラリア、オーストリア、ベルギー、カナダ、チェコシア、デンマーク、フランス、ドイツ、香港国際航空、ハンガリー、アイルランド、イタリア、マレーシア、メキシコ、オランダ、ニュージーランド、ポーランド、ポルトガル、ルーマニア、シンガポール、韓国、スペイン、スウェーデン、スイス、タイ、英国、米国</span><span class="sxs-lookup"><span data-stu-id="e77e4-151">Australia, Austria, Belgium, Canada, Czechia, Denmark, France, Germany, Hong Kong S.A.R., Hungary, Ireland, Italy, Malaysia, Mexico, Netherlands, New Zealand, Poland, Portugal, Romania, Singapore, South Korea, Spain, Sweden, Switzerland, Thailand, United Kingdom, United States</span></span> |
| `Telekom Deutschland` | <span data-ttu-id="e77e4-152">通話</span><span class="sxs-lookup"><span data-stu-id="e77e4-152">Calling</span></span> | <span data-ttu-id="e77e4-153">ドイツ</span><span class="sxs-lookup"><span data-stu-id="e77e4-153">Germany</span></span>  |
| `Telenor` | <span data-ttu-id="e77e4-154">通話</span><span class="sxs-lookup"><span data-stu-id="e77e4-154">Calling</span></span> | <span data-ttu-id="e77e4-155">デンマーク、フィンランド、ノルウェー、スウェーデン</span><span class="sxs-lookup"><span data-stu-id="e77e4-155">Denmark, Finland, Norway, Sweden</span></span>  |
| `Verizon` | <span data-ttu-id="e77e4-156">通話</span><span class="sxs-lookup"><span data-stu-id="e77e4-156">Calling</span></span> | <span data-ttu-id="e77e4-157">米国</span><span class="sxs-lookup"><span data-stu-id="e77e4-157">United States</span></span> |
