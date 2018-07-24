---
title: 変換ルールの選択
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.VoiceTrunkSelRule
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 55776a94-4888-4436-a3b6-0e6f8252e392
ROBOTS: NOINDEX, NOFOLLOW
description: エンタープライズ VoIP では、すべてのダイヤル文字列が番号の逆引き参照 (RNL) を実行するための E.164 形式に正規化する必要があります。 一方、トランク ピア (つまり、関連付けられたゲートウェイ、PBX、または SIP トランク) では、番号を地域のダイヤル形式にすることが必要な場合もあります。 E.164 形式から地域のダイヤル形式に番号を変換するには、オプションとして、トランク ピアにルーティングする前に 1 つ以上の変換ルールを定義して要求 URI を操作することができます。 たとえば、ダイヤル文字列の先頭から +44 を削除して 0144 に置き換える変換ルールを作成できます。
ms.openlocfilehash: c1a8b5e3506eea97e6f9bab7c455eb31d26f4455
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/24/2018
ms.locfileid: "20998989"
---
# <a name="select-translation-rules"></a><span data-ttu-id="16b59-106">変換ルールの選択</span><span class="sxs-lookup"><span data-stu-id="16b59-106">Select Translation Rules</span></span>
 
 <span data-ttu-id="16b59-107">エンタープライズ VoIP では、すべてのダイヤル文字列が番号の逆引き参照 (RNL) を実行するための E.164 形式に正規化する必要があります。</span><span class="sxs-lookup"><span data-stu-id="16b59-107">Enterprise Voice requires that all dial strings be normalized to E.164 format for the purpose of performing reverse number lookup (RNL).</span></span> <span data-ttu-id="16b59-108">一方、トランク ピア (つまり、関連付けられたゲートウェイ、PBX、または SIP トランク) では、番号を地域のダイヤル形式にすることが必要な場合もあります。</span><span class="sxs-lookup"><span data-stu-id="16b59-108">The trunk peer (that is, the associated gateway, PBX, or SIP trunk) may require that numbers be in a local dialing format.</span></span> <span data-ttu-id="16b59-109">E.164 形式から地域のダイヤル形式に番号を変換するには、オプションとして、トランク ピアにルーティングする前に 1 つ以上の変換ルールを定義して要求 URI を操作することができます。</span><span class="sxs-lookup"><span data-stu-id="16b59-109">To translate numbers from E.164 format to a local dialing format, you can optionally define one or more translation rules to manipulate the Request URI before routing it to the trunk peer.</span></span> <span data-ttu-id="16b59-110">たとえば、ダイヤル文字列の先頭から +44 を削除して 0144 に置き換える変換ルールを作成できます。</span><span class="sxs-lookup"><span data-stu-id="16b59-110">For example, you could write a translation rule to remove +44 from the beginning of a dial string and replace it with 0144.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="16b59-111">トランク ピアで変換ルールを構成する代わりに使用するものでは 1 つまたは複数の変換ルールをエンタープライズ VoIP のトランク構成に関連付けること。</span><span class="sxs-lookup"><span data-stu-id="16b59-111">The ability to associate one or more translation rules with an Enterprise Voice trunk configuration is intended to be used as an alternative to configuring translation rules on the trunk peer.</span></span> <span data-ttu-id="16b59-112">2 つのルールが競合する可能性がありますので、トランク ピアで変換ルールを構成している場合は、エンタープライズ VoIP のトランク構成の変換規則を関連付けないでください。</span><span class="sxs-lookup"><span data-stu-id="16b59-112">Do not associate translation rules with an Enterprise Voice trunk configuration if you have configured translation rules on the trunk peer because the two rules might conflict.</span></span> 
  
<span data-ttu-id="16b59-113">既存の変換ルールを使用するには、一覧でルールをクリックして [**OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="16b59-113">To use an existing translation rule, click a rule in the list and then click **OK**.</span></span>
  
 
  

