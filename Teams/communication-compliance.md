---
title: Microsoft Teams の通信のコンプライアンス
author: MicrosoftHeidi
ms.author: heidip
manager: serdars
ms.topic: reference
ms.service: msteams
audience: admin
ms.reviewer: anwara
description: コミュニケーションのコンプライアンスについては、「Microsoft Teams の観点からの insider リスクソリューションセットの一部 (M365 通信のコンプライアンス機能の一部)」をご覧ください。
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: bf97f4adc33b0855e986cf2baed54f69de91f4f0
ms.sourcegitcommit: c8b5d4dd70d183f7ca480fb735a19290a3457b30
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/08/2020
ms.locfileid: "45077695"
---
# <a name="communication-compliance-for-microsoft-teams"></a><span data-ttu-id="4b1d7-103">Microsoft Teams の通信のコンプライアンス</span><span class="sxs-lookup"><span data-stu-id="4b1d7-103">Communication compliance for Microsoft Teams</span></span>

<span data-ttu-id="4b1d7-104">通信のコンプライアンスは、Microsoft 365 で強化された新しい insider リスクソリューションの一部であり、組織内の不適切なメッセージに対する修復措置を検出、キャプチャし、解決するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="4b1d7-104">Communication compliance is part of the new insider risk solution set in Microsoft 365 that helps minimize communication risks by helping you detect, capture, and take remediation actions for inappropriate messages in your organization.</span></span> <span data-ttu-id="4b1d7-105">チームチャネルまたは1:1 やグループチャットで不快感を持たせたり、嫌がらせをしたりすることができます。</span><span class="sxs-lookup"><span data-stu-id="4b1d7-105">It helps in identifying Offensive language and anti-harassment in Team Channels or 1:1 and Group chats.</span></span> <span data-ttu-id="4b1d7-106">また、ポリシーを設定して、機密情報がチームチャネルまたは1:1 とグループチャットの一部として共有されているかどうかを確認することもできます。</span><span class="sxs-lookup"><span data-stu-id="4b1d7-106">You can also set policies to see if any Sensitive information is being shared as part of Team channels or 1:1 and Group chats.</span></span> <span data-ttu-id="4b1d7-107">さまざまな種類のポリシーとその設定方法の詳細については、 [「M365 の記事](https://docs.microsoft.com/microsoft-365/compliance/communication-compliance)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4b1d7-107">For more information on different types of policies and how to set up refer to the [M365 article](https://docs.microsoft.com/microsoft-365/compliance/communication-compliance).</span></span>

## <a name="how-to-use-communication-compliance-in-teams"></a><span data-ttu-id="4b1d7-108">Teams で通信のコンプライアンスを使用する方法</span><span class="sxs-lookup"><span data-stu-id="4b1d7-108">How to use communication compliance in Teams</span></span>

### <a name="identify-inappropriate-messages"></a><span data-ttu-id="4b1d7-109">不適切なメッセージを特定する</span><span class="sxs-lookup"><span data-stu-id="4b1d7-109">Identify inappropriate messages</span></span>

<span data-ttu-id="4b1d7-110">Microsoft Teams で送信されたメッセージ (1:1、グループチャット、またはチャネルの会話) を特定したい場合は、ポリシーを有効にして確認することができます。また、レビュー担当者は、メッセージを確認して、トレーニング資料を送信したり、適切な措置をとるなどの必要な手順を実行することができます。</span><span class="sxs-lookup"><span data-stu-id="4b1d7-110">If you want to identify any messages that are sent in Microsoft Teams (1:1, Group Chats or Channel conversations) contain Offensive Language or anti-harassment, you can enable policies to identify this and the reviewer can look into the messages and take necessary steps like sending training material or escalate to the right authorities.</span></span>

### <a name="identify-sensitive-or-regulatory-information"></a><span data-ttu-id="4b1d7-111">機密情報または規制情報を特定する</span><span class="sxs-lookup"><span data-stu-id="4b1d7-111">Identify sensitive or Regulatory information</span></span>

<span data-ttu-id="4b1d7-112">Microsoft Teams (1:1、グループチャット、またはチャネルでの会話) で送信されたメッセージを、機密情報や規制の種類に対してスキャンする場合は、事前に定義された機密または規制の種類をサポートするポリシーを選ぶことができます。</span><span class="sxs-lookup"><span data-stu-id="4b1d7-112">If you want to scan messages sent in Microsoft Teams (1:1, Group Chats or Channel conversations) for sensitive information or regulatory types, you can choose policies that support predefined sensitive or regulatory types.</span></span>

> [!NOTE]
> <span data-ttu-id="4b1d7-113">プライベートチャネルは、通信のコンプライアンスによってサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="4b1d7-113">Private channels are not supported by communication compliance.</span></span>

### <a name="custom-policy"></a><span data-ttu-id="4b1d7-114">カスタムポリシー</span><span class="sxs-lookup"><span data-stu-id="4b1d7-114">Custom Policy</span></span>

<span data-ttu-id="4b1d7-115">このテンプレートを使用して、特定の通信チャネル、個々の検出条件、組織内で監視およびレビューするコンテンツの量を構成します。</span><span class="sxs-lookup"><span data-stu-id="4b1d7-115">Use this template to configure specific communication channels, individual detection conditions, and the amount of content to monitor and review in your organization.</span></span>

### <a name="custom-trainable-classifier"></a><span data-ttu-id="4b1d7-116">Custom Trainable クラシファイア</span><span class="sxs-lookup"><span data-stu-id="4b1d7-116">Custom Trainable classifier</span></span>

<span data-ttu-id="4b1d7-117">Box 分類子のいずれかが目的に合わない場合は、trainable 分類子を使います。</span><span class="sxs-lookup"><span data-stu-id="4b1d7-117">Use trainable classifiers when one of the out of the box classifiers won't meet your needs.</span></span> <span data-ttu-id="4b1d7-118">Microsoft 365 分類子は、さまざまな種類のコンテンツを認識できるようにトレーニングするためのツールです。</span><span class="sxs-lookup"><span data-stu-id="4b1d7-118">A Microsoft 365 classifier is a tool you can train to recognize various types of content by giving it samples to look at.</span></span> <span data-ttu-id="4b1d7-119">分類子のトレーニングでは、最初に、ユーザーが選択してカテゴリに対してプラスのサンプルを提供する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4b1d7-119">Training the classifier involves first giving it samples that are human picked and positively match the category.</span></span> <span data-ttu-id="4b1d7-120">次に、これらのサンプルを処理した後、正と負の標本の組み合わせを指定して予測をテストします。</span><span class="sxs-lookup"><span data-stu-id="4b1d7-120">Then, after it has processed those samples, you test the predictions by giving it a mix of positive and negative samples.</span></span> <span data-ttu-id="4b1d7-121">詳細については、このトピックの詳細については、 [M365 の記事](https://docs.microsoft.com/microsoft-365/compliance/classifier-creating-a-trainable-classifier)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4b1d7-121">To Lean more about this refer to the [M365 article](https://docs.microsoft.com/microsoft-365/compliance/classifier-creating-a-trainable-classifier) for more on this topic.</span></span>

> [!NOTE]
> <span data-ttu-id="4b1d7-122">通信コンプライアンスが Exchange ハイブリッド展開をサポートするようになりました。</span><span class="sxs-lookup"><span data-stu-id="4b1d7-122">Communication compliance now supports Exchange hybrid deployments.</span></span>

<span data-ttu-id="4b1d7-123">通信のコンプライアンスは、ポリシーに一致するすべてのメッセージの会話履歴をサポートします。</span><span class="sxs-lookup"><span data-stu-id="4b1d7-123">Communication compliance supports conversation history for any messages that match the polices.</span></span> <span data-ttu-id="4b1d7-124">これにより、調査管理者にコンテキストが提供されます。</span><span class="sxs-lookup"><span data-stu-id="4b1d7-124">This provides context to the investigating admin.</span></span>

:::image type="content" source="media/communication-compliance-1.png" alt-text="Microsoft Teams での通信のコンプライアンスのための画面。":::

## <a name="where-communication-policies-can-be-applied-in-teams"></a><span data-ttu-id="4b1d7-126">チームで通信ポリシーを適用できる場所</span><span class="sxs-lookup"><span data-stu-id="4b1d7-126">Where communication policies can be applied in Teams</span></span>

<span data-ttu-id="4b1d7-127">通信コンプライアンスポリシーをセットアップして、Teams で送信されたメッセージを次のレベルで設定することができます。</span><span class="sxs-lookup"><span data-stu-id="4b1d7-127">Communication compliance policies can be setup for messages sent in Teams at the following levels:</span></span>

- <span data-ttu-id="4b1d7-128">ユーザーレベル: 管理者は、個々のユーザーレベルでポリシーを設定したり、テナントのすべてのユーザーに適用したりすることができます。</span><span class="sxs-lookup"><span data-stu-id="4b1d7-128">User level : An admin can set up policies at an individual user level or apply it to all the users on the tenant.</span></span> <span data-ttu-id="4b1d7-129">これは、ユーザーが1:1 またはグループチャットで送信したメッセージのみを対象とします。</span><span class="sxs-lookup"><span data-stu-id="4b1d7-129">This will only covers messages that a user sent in 1:1 or Group chats.</span></span>
- <span data-ttu-id="4b1d7-130">チームレベル: 管理者は、チームでポリシーを設定することもできます。</span><span class="sxs-lookup"><span data-stu-id="4b1d7-130">Team Level: An admin can also set up policies on a team.</span></span> <span data-ttu-id="4b1d7-131">これにより、そのチームのチャネルで送信されたすべてのメッセージ (プライベートチャネルメッセージはサポートされません) が対象となります。</span><span class="sxs-lookup"><span data-stu-id="4b1d7-131">This covers all the messages sent in the channel in that team (Private channel messages are not supported).</span></span>
