---
title: アナログ デバイスの移行
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Skype for Business Server は、アナログデバイスをサポートしています。 特に、サポートされているアナログデバイスはアナログオーディオ電話とアナログ fax マシンです。 Skype for Business Server 環境でのアナログデバイスの使用をサポートするために、修飾ゲートウェイを構成することができます。 Skype for Business Server 2019 に移行した後は、アナログデバイスに関連付けられた連絡先オブジェクトも移行する必要があります。 Skype for Business Server 管理シェルを使って、従来のアナログデバイスに関連付けられたすべての連絡先オブジェクトを取得してから、それらのオブジェクトを Skype for Business Server 2019 プールに移動します。
ms.openlocfilehash: a822f8f73ad839654d266182172ef8e30d5d28e8
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34280844"
---
# <a name="migrate-analog-devices"></a><span data-ttu-id="6babc-107">アナログ デバイスの移行</span><span class="sxs-lookup"><span data-stu-id="6babc-107">Migrate analog devices</span></span>

<span data-ttu-id="6babc-108">Skype for Business Server は、アナログデバイスをサポートしています。</span><span class="sxs-lookup"><span data-stu-id="6babc-108">Skype for Business Server provides support for analog devices.</span></span> <span data-ttu-id="6babc-109">特に、サポートされているアナログデバイスはアナログオーディオ電話とアナログ fax マシンです。</span><span class="sxs-lookup"><span data-stu-id="6babc-109">Specifically, the supported analog devices are analog audio phones and analog fax machines.</span></span> <span data-ttu-id="6babc-110">Skype for Business Server 環境でのアナログデバイスの使用をサポートするために、修飾ゲートウェイを構成することができます。</span><span class="sxs-lookup"><span data-stu-id="6babc-110">You can configure the qualified gateways to support the use of analog devices in your Skype for Business Server environment.</span></span> <span data-ttu-id="6babc-111">Skype for Business Server 2019 に移行した後は、アナログデバイスに関連付けられた連絡先オブジェクトも移行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6babc-111">After you migrate to Skype for Business Server 2019, you must also migrate the contact objects associated with the analog devices.</span></span> <span data-ttu-id="6babc-112">Skype for Business Server 管理シェルを使って、従来のアナログデバイスに関連付けられたすべての連絡先オブジェクトを取得してから、それらのオブジェクトを Skype for Business Server 2019 プールに移動します。</span><span class="sxs-lookup"><span data-stu-id="6babc-112">Use Skype for Business Server Management Shell to first retrieve all contact objects associated with the legacy analog devices, and then move those objects to the Skype for Business Server 2019 pool.</span></span>

### <a name="to-migrate-analog-devices"></a><span data-ttu-id="6babc-113">アナログデバイスを移行するには</span><span class="sxs-lookup"><span data-stu-id="6babc-113">To migrate analog devices</span></span>

1. <span data-ttu-id="6babc-114">Skype for Business Server 管理シェルを開始します。 [**スタート**] をクリックし、[**すべてのプログラム**]、[ **Microsoft skype for business Server 2019**]、[ **skype for business server 管理シェル**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="6babc-114">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Skype for Business Server 2019**, and then click **Skype for Business Server Management Shell**.</span></span>

2. <span data-ttu-id="6babc-115">コマンド ラインで次を入力します。</span><span class="sxs-lookup"><span data-stu-id="6babc-115">At the command line, type:</span></span>

   ```
   Get-CsAnalogDevice -Filter {RegistrarPool -eq "pool01.contoso.net"} | Move-CsAnalogDevice -Target pool02.contoso.net
   ```

3. <span data-ttu-id="6babc-116">すべての連絡先オブジェクトが Skype for Business Server 2019 プールに移動されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="6babc-116">Verify that all contact objects have been moved to the Skype for Business Server 2019 pool.</span></span> <span data-ttu-id="6babc-117">コマンド ラインで次を入力します。</span><span class="sxs-lookup"><span data-stu-id="6babc-117">At the command line, type:</span></span>

   ```
   Get-CsAnalogDevice -Filter {RegistrarPool -eq "pool02.contoso.net"}
   ```

4. <span data-ttu-id="6babc-118">すべての連絡先オブジェクトが Skype for Business Server 2019 プールに関連付けられていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="6babc-118">Verify that all the contact objects are now associated with the Skype for Business Server 2019 pool.</span></span>


