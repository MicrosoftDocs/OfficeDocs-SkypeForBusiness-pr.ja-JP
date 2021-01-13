---
title: Skype for Business で IP アドレスの種類を構成する
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 17e756c0-6652-4cd5-b185-4b25929e3a42
description: '概要: Skype for Business Server を実装する前に、以下の IP アドレスの種類に関する考慮事項を確認してください。'
ms.openlocfilehash: d5e50b8d3a964bb4e4dcbc502527e5249af3a1e9
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49825263"
---
# <a name="configure-ip-address-types-in-skype-for-business"></a><span data-ttu-id="7237f-103">Skype for Business で IP アドレスの種類を構成する</span><span class="sxs-lookup"><span data-stu-id="7237f-103">Configure IP address types in Skype for Business</span></span>

<span data-ttu-id="7237f-104">**概要:** Skype for Business Server を実装する前に、以下の IP アドレスの種類に関する考慮事項を確認してください。</span><span class="sxs-lookup"><span data-stu-id="7237f-104">**Summary:** Review the IP Address type considerations below before implementing Skype for Business Server.</span></span>

<span data-ttu-id="7237f-105">IP アドレスの種類は、トポロジ ビルダーで構成したトポロジ設定を使用して展開します。</span><span class="sxs-lookup"><span data-stu-id="7237f-105">You deploy IP address types by using topology settings that you configure in Topology Builder.</span></span> <span data-ttu-id="7237f-106">このセクションでは、フロントエンド サーバー、仲介サーバー、およびエッジ サーバーに IP アドレスの種類を展開する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="7237f-106">This section describes how to deploy IP address types on Front End Servers, Mediation Servers, and Edge Servers.</span></span>

## <a name="deploy-ip-address-types-on-a-front-end-server"></a><span data-ttu-id="7237f-107">フロントエンド サーバーに IP アドレスの種類を展開する</span><span class="sxs-lookup"><span data-stu-id="7237f-107">Deploy IP address types on a Front End Server</span></span>

<span data-ttu-id="7237f-108">トポロジ ビルダーを使用して、以下の手順を実行して、IP アドレスの種類をフロントエンド サーバーに展開します。</span><span class="sxs-lookup"><span data-stu-id="7237f-108">Using Topology Builder, perform the steps in the following procedure to deploy IP address types on a Front End Server.</span></span>

### <a name="to-deploy-ip-address-types-on-a-front-end-server"></a><span data-ttu-id="7237f-109">IP アドレス タイプをフロントエンド サーバーに展開するには</span><span class="sxs-lookup"><span data-stu-id="7237f-109">To deploy IP address types on a Front End Server</span></span>

1. <span data-ttu-id="7237f-p102">[**Enterprise Edition フロントエンドのプール**] で、プール内のサーバーを右クリックし、[**プロパティの編集**] を選択します (または、サーバーを選択し、[**アクション**] メニューの [**プロパティの編集**] をクリックします)。</span><span class="sxs-lookup"><span data-stu-id="7237f-p102">Under **Enterprise Edition Front End pools**, right-click the server within a pool, and then select **Edit Properties**. (Alternatively, select the server, and then click **Edit Properties** from the **Action** menu.)</span></span>

2. <span data-ttu-id="7237f-112">[**プロパティの編集**] ダイアログ ボックスで、構成する IP アドレス タイプを選択します。</span><span class="sxs-lookup"><span data-stu-id="7237f-112">In the **Edit Properties** dialog box, select the IP address type that you want to configure.</span></span> <span data-ttu-id="7237f-113">デュアル スタック構成の場合は **、[IPv4** を有効にして IPv6 を有効にする **] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="7237f-113">For a dual-stack configuration, select **Enable IPv4** and **Enable IPv6**.</span></span>

   <span data-ttu-id="7237f-114">**フロントエンド サーバー プールの [プロパティの編集] ダイアログ ボックス**</span><span class="sxs-lookup"><span data-stu-id="7237f-114">**Edit Properties dialog box for the Front End Server pool**</span></span>

   - <span data-ttu-id="7237f-p104">[**すべての構成済み IP アドレスを使用する**]。コンピューター上で定義されているすべての IP アドレスの使用を許可する場合は、このオプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="7237f-p104">**Use all configured IP addresses**. Select this option if you want to allow any IP address defined on the computer to be used.</span></span>

     > [!NOTE]
     > <span data-ttu-id="7237f-117">これは、IP version 6 (IPv6) 構成の推奨オプションです。</span><span class="sxs-lookup"><span data-stu-id="7237f-117">This is the recommended option for IP version 6 (IPv6) configurations.</span></span>

   - <span data-ttu-id="7237f-p105">[**サービスの使用を選択した IP アドレスに限定する**]。新しいサーバーで使用するアドレスを指定するには、このオプションを選択します。このオプションを選択した場合は、[**プライマリ IP アドレス**] に値を入力する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7237f-p105">**Limit service usage to selected IP addresses**. Select this option to specify a specific address to use on the new server. If you select this option, you must enter a value for **Primary IP address**.</span></span>

   - <span data-ttu-id="7237f-p106">[**プライマリ IP アドレス**]。公衆交換電話網 (PSTN) 以外のすべての通信でサーバーが使用する IP アドレスを入力します。入力する IP アドレスは、選択されているアドレス タイプの形式に一致している必要があります。</span><span class="sxs-lookup"><span data-stu-id="7237f-p106">**Primary IP address**. Enter an IP address that the server will use for all communications except public switched telephone network (PSTN). The IP address entered must match the format of the select address type.</span></span>

   - <span data-ttu-id="7237f-p107">[**PSTN IP アドレス**]。フロントエンド サーバーで仲介サーバーが共存する場合は、PSTN IP アドレスを定義します。このアドレスは、選択されているアドレス タイプの形式に一致している必要があります。</span><span class="sxs-lookup"><span data-stu-id="7237f-p107">**PSTN IP address**. Define a PSTN IP address when a Mediation Server is collocated on the Front End Server. This address must match the format of the selected address type.</span></span>

> [!NOTE]
> <span data-ttu-id="7237f-127">フロント エンド サーバーでの PSTN IP アドレス構成 (または何らかの理由で) をサポートする追加のネットワーク インターフェイス カード (NIC) のインストールはサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="7237f-127">The installation of additional network interface cards (NICs) to support the PSTN IP address configuration (or for any other reason) on Front End Servers is not supported.</span></span> <span data-ttu-id="7237f-128">Skype for Business Server でサポートされる NIC 構成の詳細については [、Lync Server 2013](https://technet.microsoft.com/library/c964c1c0-0153-472b-88ad-a38866e0df0c.aspx)のサーバー ハードウェア プラットフォームを参照してください。</span><span class="sxs-lookup"><span data-stu-id="7237f-128">For more information about supported NIC configurations for Skype for Business Server, see [Server hardware platforms for Lync Server 2013](https://technet.microsoft.com/library/c964c1c0-0153-472b-88ad-a38866e0df0c.aspx).</span></span>

## <a name="deploy-ip-address-types-on-a-mediation-server"></a><span data-ttu-id="7237f-129">仲介サーバーに IP アドレスの種類を展開する</span><span class="sxs-lookup"><span data-stu-id="7237f-129">Deploy IP address types on a Mediation Server</span></span>

<span data-ttu-id="7237f-130">トポロジ ビルダーを使用して、以下の手順を実行して、仲介サーバーに IP アドレスの種類を展開します。</span><span class="sxs-lookup"><span data-stu-id="7237f-130">Using Topology Builder, perform the steps in the following procedure to deploy IP address types on a Mediation Server.</span></span>

### <a name="to-deploy-ip-address-types-on-a-mediation-server"></a><span data-ttu-id="7237f-131">仲介サーバーに IP アドレス タイプを展開するには</span><span class="sxs-lookup"><span data-stu-id="7237f-131">To deploy IP address types on a Mediation Server</span></span>

- <span data-ttu-id="7237f-132">トポロジ ビルダーの仲介プール **で**、プール内のサーバーを右クリックし、[プロパティの編集] **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="7237f-132">In Topology Builder, under **Mediation pools**, right-click the server within a pool, and then select **Edit Properties**.</span></span> <span data-ttu-id="7237f-133">(または、サーバーを選択し、[操作] メニューの **[プロパティの** 編集 **] をクリック** します)。</span><span class="sxs-lookup"><span data-stu-id="7237f-133">(Alternatively, select the server, and then click **Edit Properties** from the **Action** menu.)</span></span>

- <span data-ttu-id="7237f-p110">[**プロパティの編集**] ダイアログ ボックスで、構成する IP アドレス タイプを選択します。デュアル スタック構成の場合は、次の図のように、[**IPv4 を有効にする**] および [**IPv6 を有効にする**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="7237f-p110">In the **Edit Properties** dialog box, select the IP address type that you want to configure. For a dual-stack configuration, select **Enable IPv4** and **Enable IPv6**, as shown in the following figure.</span></span>

   <span data-ttu-id="7237f-136">**仲介サーバー プールの [プロパティの編集] ダイアログ ボックス**</span><span class="sxs-lookup"><span data-stu-id="7237f-136">**Edit Properties dialog box for the Mediation Server pool**</span></span>

  - <span data-ttu-id="7237f-p111">[**すべての構成済み IP アドレスを使用する**]。コンピューター上で定義されているすべての IP アドレスの使用を許可する場合は、このオプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="7237f-p111">**Use all configured IP addresses**. Select this option if you want to allow any IP address defined on the computer to be used.</span></span>

    > [!NOTE]
    > <span data-ttu-id="7237f-139">これは、IP version 6 (IPv6) 構成の推奨オプションです。</span><span class="sxs-lookup"><span data-stu-id="7237f-139">This is the recommended option for IP version 6 (IPv6) configurations.</span></span>

  - <span data-ttu-id="7237f-p112">[**サービスの使用を、指定したアドレスに制限する**]。新しいサーバーで使用する特定のアドレスを指定する場合は、このオプションを選択します。このオプションを選択する場合は、プライマリ IP アドレスの値を入力する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7237f-p112">**Limit service usage to selected IP addresses**. Select this option to specify a specific address to use on the new server. If you select this option, you must enter a value for Primary IP address.</span></span>

  - <span data-ttu-id="7237f-p113">[**プライマリ IP アドレス**]。公衆交換電話網 (PSTN) 以外のすべての通信でサーバーが使用する IP アドレスを入力します。入力する IP アドレスは、選択されているアドレス タイプの形式に一致している必要があります。</span><span class="sxs-lookup"><span data-stu-id="7237f-p113">**Primary IP address**. Enter an IP address that the server will use for all communications except public switched telephone network (PSTN). The IP address entered must match the format of the select address type.</span></span>

  - <span data-ttu-id="7237f-p114">[**PSTN IP アドレス**]。フロントエンド サーバーで仲介サーバーが共存する場合は、PSTN IP アドレスを定義します。このアドレスは、選択されているアドレス タイプの形式に一致している必要があります。</span><span class="sxs-lookup"><span data-stu-id="7237f-p114">**PSTN IP address**. Define a PSTN IP address when a Mediation Server is collocated on the Front End Server. This address must match the format of the selected address type.</span></span>
> [!IMPORTANT]
> <span data-ttu-id="7237f-149">専用の仲介サーバーでサポートされるネットワーク カード *は 2* つのみです。</span><span class="sxs-lookup"><span data-stu-id="7237f-149">We only support two network cards on *dedicated* Mediation Servers.</span></span> <span data-ttu-id="7237f-150">仲介 Sserver の役割がフロントエンドに一重に展開されている場合、デュアル ネットワーク カードはサポートされません。</span><span class="sxs-lookup"><span data-stu-id="7237f-150">If the Mediation Sserver role is collocated on the Front End, then dual network cards are not supported.</span></span> 

> [!NOTE]
> - <span data-ttu-id="7237f-151">Skype for Business Server 2015 でサポートされる NIC 構成の詳細については[、「Hardware for Skype for Business Server 2015」](../requirements-for-your-environment/server-requirements.md#hardware-for-skype-for-business-server-2015)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7237f-151">For more information about supported NIC configurations for Skype for Business Server 2015, see [Hardware for Skype for Business Server 2015](../requirements-for-your-environment/server-requirements.md#hardware-for-skype-for-business-server-2015)</span></span>
> - <span data-ttu-id="7237f-152">Skype for Business Server 2019 でサポートされる NIC 構成の詳細については[、「Hardware for Skype for Business Server 2019」](../../../SfBServer2019/plan/system-requirements.md#hardware-for-skype-for-business-server-2019)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7237f-152">For more information about supported NIC configurations for Skype for Business Server 2019, see [Hardware for Skype for Business Server 2019](../../../SfBServer2019/plan/system-requirements.md#hardware-for-skype-for-business-server-2019)</span></span>



## <a name="deploy-ip-address-types-on-an-edge-server"></a><span data-ttu-id="7237f-153">IP アドレスの種類をエッジ サーバーに展開する</span><span class="sxs-lookup"><span data-stu-id="7237f-153">Deploy IP address types on an Edge Server</span></span>

<span data-ttu-id="7237f-154">トポロジ ビルダーを使用して、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="7237f-154">Using Topology Builder, perform the following steps:</span></span>

### <a name="to-deploy-ip-address-types-on-an-edge-server"></a><span data-ttu-id="7237f-155">エッジ サーバー上に IP アドレスの種類を展開するには</span><span class="sxs-lookup"><span data-stu-id="7237f-155">To deploy IP address types on an Edge Server</span></span>

1. <span data-ttu-id="7237f-156">トポロジ ビルダーのエッジ プール **で**、プール内のサーバーを右クリックし、[プロパティの編集] **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="7237f-156">In Topology Builder, under **Edge pools**, right-click the server within a pool, and then select **Edit Properties**.</span></span> <span data-ttu-id="7237f-157">(または、サーバーを選択し、[操作] メニューの **[プロパティの** 編集 **] をクリック** します)。</span><span class="sxs-lookup"><span data-stu-id="7237f-157">(Alternatively, select the server, and then click **Edit Properties** from the **Action** menu.)</span></span>

2. <span data-ttu-id="7237f-158">[**プロパティの編集**] ウィンドウで、サポートする IP アドレス構成を選択します。</span><span class="sxs-lookup"><span data-stu-id="7237f-158">In the **Edit Properties** window, select the IP address configuration that you want to support.</span></span>

3. <span data-ttu-id="7237f-159">選択したアドレスの種類のそれぞれで、適切な内部アドレスと外部アドレスを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7237f-159">For each address type that you select, you must supply appropriate internal and external addresses.</span></span>
