---
title: アナログ デバイスの移行
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: ビジネス サーバーの Skype では、アナログ デバイスのサポートを提供します。 具体的には、サポートされているアナログ デバイスは、アナログ音声電話とアナログ fax 機器です。 ビジネス サーバー環境に、Skype でのアナログ デバイスの使用をサポートするために修飾されたゲートウェイを構成できます。 ビジネス サーバー 2019 のように Skype に移行した後も、アナログ デバイスに関連付けられている連絡先オブジェクトを移行する必要があります。 最初にすべてを取得するためにビジネスのサーバー管理シェルを使用して Skype では、レガシーのアナログ デバイスに関連付けられているオブジェクトに連絡し、ビジネス サーバー 2019 プールの Skype にそれらのオブジェクトを移動します。
ms.openlocfilehash: 80edf5b806ffd192d125bd5da27207a37f3074d1
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "32238391"
---
# <a name="migrate-analog-devices"></a><span data-ttu-id="68840-107">アナログ デバイスの移行</span><span class="sxs-lookup"><span data-stu-id="68840-107">Migrate analog devices</span></span>

<span data-ttu-id="68840-108">ビジネス サーバーの Skype では、アナログ デバイスのサポートを提供します。</span><span class="sxs-lookup"><span data-stu-id="68840-108">Skype for Business Server provides support for analog devices.</span></span> <span data-ttu-id="68840-109">具体的には、サポートされているアナログ デバイスは、アナログ音声電話とアナログ fax 機器です。</span><span class="sxs-lookup"><span data-stu-id="68840-109">Specifically, the supported analog devices are analog audio phones and analog fax machines.</span></span> <span data-ttu-id="68840-110">ビジネス サーバー環境に、Skype でのアナログ デバイスの使用をサポートするために修飾されたゲートウェイを構成できます。</span><span class="sxs-lookup"><span data-stu-id="68840-110">You can configure the qualified gateways to support the use of analog devices in your Skype for Business Server environment.</span></span> <span data-ttu-id="68840-111">ビジネス サーバー 2019 のように Skype に移行した後も、アナログ デバイスに関連付けられている連絡先オブジェクトを移行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="68840-111">After you migrate to Skype for Business Server 2019, you must also migrate the contact objects associated with the analog devices.</span></span> <span data-ttu-id="68840-112">最初にすべてを取得するためにビジネスのサーバー管理シェルを使用して Skype では、レガシーのアナログ デバイスに関連付けられているオブジェクトに連絡し、ビジネス サーバー 2019 プールの Skype にそれらのオブジェクトを移動します。</span><span class="sxs-lookup"><span data-stu-id="68840-112">Use Skype for Business Server Management Shell to first retrieve all contact objects associated with the legacy analog devices, and then move those objects to the Skype for Business Server 2019 pool.</span></span>

### <a name="to-migrate-analog-devices"></a><span data-ttu-id="68840-113">アナログ デバイスを移行するには</span><span class="sxs-lookup"><span data-stu-id="68840-113">To migrate analog devices</span></span>

1. <span data-ttu-id="68840-114">ビジネス サーバー管理シェルには、Skype を起動する: [**スタート**] ボタン、[**すべてのプログラム**] をクリックして、**ビジネス サーバー 2019 の Skype をマイクロソフト**をクリック**ビジネス サーバー管理シェルの Skype**です。</span><span class="sxs-lookup"><span data-stu-id="68840-114">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Skype for Business Server 2019**, and then click **Skype for Business Server Management Shell**.</span></span>

2. <span data-ttu-id="68840-115">コマンド ラインで次を入力します。</span><span class="sxs-lookup"><span data-stu-id="68840-115">At the command line, type:</span></span>

   ```
   Get-CsAnalogDevice -Filter {RegistrarPool -eq "pool01.contoso.net"} | Move-CsAnalogDevice -Target pool02.contoso.net
   ```

3. <span data-ttu-id="68840-116">連絡先のすべてのオブジェクト移動されている、Skype をビジネス サーバー 2019 プールのことを確認します。</span><span class="sxs-lookup"><span data-stu-id="68840-116">Verify that all contact objects have been moved to the Skype for Business Server 2019 pool.</span></span> <span data-ttu-id="68840-117">コマンド ラインで次を入力します。</span><span class="sxs-lookup"><span data-stu-id="68840-117">At the command line, type:</span></span>

   ```
   Get-CsAnalogDevice -Filter {RegistrarPool -eq "pool02.contoso.net"}
   ```

4. <span data-ttu-id="68840-118">連絡先オブジェクトがすべて表示されていることを確認して、Skype のビジネス サーバー 2019 プールに関連付けられています。</span><span class="sxs-lookup"><span data-stu-id="68840-118">Verify that all the contact objects are now associated with the Skype for Business Server 2019 pool.</span></span>


