---
title: 変換ルールの選択
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/24/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.lscp.VoiceTrunkSelRule
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 55776a94-4888-4436-a3b6-0e6f8252e392
description: エンタープライズ VoIP、逆引き番号検索 (RNL) を実行するために、すべてのダイヤル文字列を E.164 形式に正規化する必要があります。 一方、トランク ピア (つまり、関連付けられたゲートウェイ、PBX、または SIP トランク) では、番号を地域のダイヤル形式にすることが必要な場合もあります。 E.164 形式から地域のダイヤル形式に番号を変換するには、オプションとして、トランク ピアにルーティングする前に 1 つ以上の変換ルールを定義して Request URI を操作することができます。 たとえば、ダイヤル文字列の先頭から +44 を削除して 0144 に置き換える変換ルールを作成できます。
ms.openlocfilehash: 3f448a9ac97c2bc7b57a8a87a6544ad84472e65e
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49803697"
---
# <a name="select-translation-rules"></a><span data-ttu-id="7b3c0-106">変換ルールの選択</span><span class="sxs-lookup"><span data-stu-id="7b3c0-106">Select Translation Rules</span></span>
 
 <span data-ttu-id="7b3c0-107">エンタープライズ VoIP、逆引き番号検索 (RNL) を実行するために、すべてのダイヤル文字列を E.164 形式に正規化する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7b3c0-107">Enterprise Voice requires that all dial strings be normalized to E.164 format for the purpose of performing reverse number lookup (RNL).</span></span> <span data-ttu-id="7b3c0-108">一方、トランク ピア (つまり、関連付けられたゲートウェイ、PBX、または SIP トランク) では、番号を地域のダイヤル形式にすることが必要な場合もあります。</span><span class="sxs-lookup"><span data-stu-id="7b3c0-108">The trunk peer (that is, the associated gateway, PBX, or SIP trunk) may require that numbers be in a local dialing format.</span></span> <span data-ttu-id="7b3c0-109">E.164 形式から地域のダイヤル形式に番号を変換するには、オプションとして、トランク ピアにルーティングする前に 1 つ以上の変換ルールを定義して Request URI を操作することができます。</span><span class="sxs-lookup"><span data-stu-id="7b3c0-109">To translate numbers from E.164 format to a local dialing format, you can optionally define one or more translation rules to manipulate the Request URI before routing it to the trunk peer.</span></span> <span data-ttu-id="7b3c0-110">たとえば、ダイヤル文字列の先頭から +44 を削除して 0144 に置き換える変換ルールを作成できます。</span><span class="sxs-lookup"><span data-stu-id="7b3c0-110">For example, you could write a translation rule to remove +44 from the beginning of a dial string and replace it with 0144.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="7b3c0-111">1 つ以上の変換ルールをエンタープライズ VoIP のトランク構成と関連付ける機能は、トランク ピアに変換ルールを構成することの代替として使用されます。</span><span class="sxs-lookup"><span data-stu-id="7b3c0-111">The ability to associate one or more translation rules with an Enterprise Voice trunk configuration is intended to be used as an alternative to configuring translation rules on the trunk peer.</span></span> <span data-ttu-id="7b3c0-112">トランク ピアで変換ルールを構成した場合は、2 つのルールが競合する可能性があるため、変換ルールをエンタープライズ VoIP トランク構成に関連付けないでください。</span><span class="sxs-lookup"><span data-stu-id="7b3c0-112">Do not associate translation rules with an Enterprise Voice trunk configuration if you have configured translation rules on the trunk peer because the two rules might conflict.</span></span> 
  
<span data-ttu-id="7b3c0-113">既存の変換ルールを使用するには、一覧でルールをクリックして [**OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="7b3c0-113">To use an existing translation rule, click a rule in the list and then click **OK**.</span></span>
  
<span data-ttu-id="7b3c0-114">Skype for Business Server コントロール パネルを使用して実行できるさまざまな手順の詳細については [、「Skype for Business Server 2015](../../manage/manage.md)の管理」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7b3c0-114">For details about the different procedures that you can perform by using the Skype for Business Server Control Panel, see [Manage Skype for Business Server 2015](../../manage/manage.md).</span></span>
  

