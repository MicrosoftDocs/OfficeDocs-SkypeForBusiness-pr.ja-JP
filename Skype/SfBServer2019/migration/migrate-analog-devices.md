---
title: アナログ デバイスの移行
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Skype for Business Server は、アナログデバイスのサポートを提供します。 具体的には、アナログ音声電話とアナログ FAX 電話がアナログ デバイスとしてサポートされます。 Skype for Business Server 環境でのアナログデバイスの使用をサポートするために、認定ゲートウェイを構成することができます。 Skype for Business Server 2019 に移行した後で、アナログデバイスに関連付けられている連絡先オブジェクトも移行する必要があります。 Skype for Business Server 管理シェルを使用して、従来のアナログデバイスに関連付けられているすべての連絡先オブジェクトを最初に取得し、そのオブジェクトを Skype for Business Server 2019 プールに移動します。
ms.openlocfilehash: 7b90a52486725c2cf30856dc643660d569d698e2
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/16/2020
ms.locfileid: "44752829"
---
# <a name="migrate-analog-devices"></a><span data-ttu-id="00f8a-107">アナログ デバイスの移行</span><span class="sxs-lookup"><span data-stu-id="00f8a-107">Migrate analog devices</span></span>

<span data-ttu-id="00f8a-108">Skype for Business Server は、アナログデバイスのサポートを提供します。</span><span class="sxs-lookup"><span data-stu-id="00f8a-108">Skype for Business Server provides support for analog devices.</span></span> <span data-ttu-id="00f8a-109">具体的には、アナログ音声電話とアナログ FAX 電話がアナログ デバイスとしてサポートされます。</span><span class="sxs-lookup"><span data-stu-id="00f8a-109">Specifically, the supported analog devices are analog audio phones and analog fax machines.</span></span> <span data-ttu-id="00f8a-110">Skype for Business Server 環境でのアナログデバイスの使用をサポートするために、認定ゲートウェイを構成することができます。</span><span class="sxs-lookup"><span data-stu-id="00f8a-110">You can configure the qualified gateways to support the use of analog devices in your Skype for Business Server environment.</span></span> <span data-ttu-id="00f8a-111">Skype for Business Server 2019 に移行した後で、アナログデバイスに関連付けられている連絡先オブジェクトも移行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="00f8a-111">After you migrate to Skype for Business Server 2019, you must also migrate the contact objects associated with the analog devices.</span></span> <span data-ttu-id="00f8a-112">Skype for Business Server 管理シェルを使用して、従来のアナログデバイスに関連付けられているすべての連絡先オブジェクトを最初に取得し、そのオブジェクトを Skype for Business Server 2019 プールに移動します。</span><span class="sxs-lookup"><span data-stu-id="00f8a-112">Use Skype for Business Server Management Shell to first retrieve all contact objects associated with the legacy analog devices, and then move those objects to the Skype for Business Server 2019 pool.</span></span>

### <a name="to-migrate-analog-devices"></a><span data-ttu-id="00f8a-113">アナログ デバイスを移行するには</span><span class="sxs-lookup"><span data-stu-id="00f8a-113">To migrate analog devices</span></span>

1. <span data-ttu-id="00f8a-114">Skype for Business Server 管理シェルを起動します。 [**スタート**]、[**すべてのプログラム**]、[ **Microsoft Skype for business Server 2019**]、[ **skype for business server 管理シェル**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="00f8a-114">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Skype for Business Server 2019**, and then click **Skype for Business Server Management Shell**.</span></span>

2. <span data-ttu-id="00f8a-115">コマンドラインで、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="00f8a-115">At the command line, type:</span></span>

   ```PowerShell
   Get-CsAnalogDevice -Filter {RegistrarPool -eq "pool01.contoso.net"} | Move-CsAnalogDevice -Target pool02.contoso.net
   ```

3. <span data-ttu-id="00f8a-116">すべての連絡先オブジェクトが Skype for Business Server 2019 プールに移動されたことを確認します。</span><span class="sxs-lookup"><span data-stu-id="00f8a-116">Verify that all contact objects have been moved to the Skype for Business Server 2019 pool.</span></span> <span data-ttu-id="00f8a-117">コマンドラインで、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="00f8a-117">At the command line, type:</span></span>

   ```PowerShell
   Get-CsAnalogDevice -Filter {RegistrarPool -eq "pool02.contoso.net"}
   ```

4. <span data-ttu-id="00f8a-118">すべての連絡先オブジェクトが Skype for Business Server 2019 プールに関連付けられていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="00f8a-118">Verify that all the contact objects are now associated with the Skype for Business Server 2019 pool.</span></span>


