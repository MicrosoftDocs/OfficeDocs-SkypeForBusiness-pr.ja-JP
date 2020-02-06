---
title: Skype for Business での IP アドレスの種類の構成
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
description: '概要: Skype for Business Server を実装する前に、次の IP アドレスの種類に関する考慮事項を確認してください。'
ms.openlocfilehash: 74cb0738c7c6eb0518d8ab4ed4fae7db66921bfb
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41802117"
---
# <a name="configure-ip-address-types-in-skype-for-business"></a><span data-ttu-id="0343b-103">Skype for Business での IP アドレスの種類の構成</span><span class="sxs-lookup"><span data-stu-id="0343b-103">Configure IP address types in Skype for Business</span></span>

<span data-ttu-id="0343b-104">**概要:** Skype for Business Server を実装する前に、次の IP アドレスの種類に関する考慮事項を確認してください。</span><span class="sxs-lookup"><span data-stu-id="0343b-104">**Summary:** Review the IP Address type considerations below before implementing Skype for Business Server.</span></span>

<span data-ttu-id="0343b-105">IP アドレスの種類を展開するには、トポロジビルダーで構成したトポロジ設定を使用します。</span><span class="sxs-lookup"><span data-stu-id="0343b-105">You deploy IP address types by using topology settings that you configure in Topology Builder.</span></span> <span data-ttu-id="0343b-106">このセクションでは、フロントエンドサーバー、仲介サーバー、およびエッジサーバーに IP アドレスの種類を展開する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="0343b-106">This section describes how to deploy IP address types on Front End Servers, Mediation Servers, and Edge Servers.</span></span>

## <a name="deploy-ip-address-types-on-a-front-end-server"></a><span data-ttu-id="0343b-107">IP アドレス タイプをフロント エンド サーバーに展開する</span><span class="sxs-lookup"><span data-stu-id="0343b-107">Deploy IP address types on a Front End Server</span></span>

<span data-ttu-id="0343b-108">トポロジビルダーを使用して、次の手順を実行して、フロントエンドサーバーに IP アドレスの種類を展開します。</span><span class="sxs-lookup"><span data-stu-id="0343b-108">Using Topology Builder, perform the steps in the following procedure to deploy IP address types on a Front End Server.</span></span>

### <a name="to-deploy-ip-address-types-on-a-front-end-server"></a><span data-ttu-id="0343b-109">IP アドレスの種類をフロントエンド サーバーに展開するには</span><span class="sxs-lookup"><span data-stu-id="0343b-109">To deploy IP address types on a Front End Server</span></span>

1. <span data-ttu-id="0343b-p102">[**Enterprise Edition フロントエンドのプール**] で、プール内のサーバーを右クリックし、[**プロパティの編集**] を選択します (または、サーバーを選択し、[**アクション**] メニューの [**プロパティの編集**] をクリックします)。</span><span class="sxs-lookup"><span data-stu-id="0343b-p102">Under **Enterprise Edition Front End pools**, right-click the server within a pool, and then select **Edit Properties**. (Alternatively, select the server, and then click **Edit Properties** from the **Action** menu.)</span></span>

2. <span data-ttu-id="0343b-112">[**プロパティの編集**] ダイアログ ボックスで、構成する IP アドレスの種類を選択します。</span><span class="sxs-lookup"><span data-stu-id="0343b-112">In the **Edit Properties** dialog box, select the IP address type that you want to configure.</span></span> <span data-ttu-id="0343b-113">デュアルスタック構成の場合は、[ **IPv4 を有効に**し、 **IPv6 を有効**にする] を選択します。</span><span class="sxs-lookup"><span data-stu-id="0343b-113">For a dual-stack configuration, select **Enable IPv4** and **Enable IPv6**.</span></span>

   <span data-ttu-id="0343b-114">**フロントエンド サーバー プールの [プロパティの編集] ダイアログ ボックス**</span><span class="sxs-lookup"><span data-stu-id="0343b-114">**Edit Properties dialog box for the Front End Server pool**</span></span>

   - <span data-ttu-id="0343b-p104">[**すべての構成済み IP アドレスを使用する**]。コンピューター上で定義されているすべての IP アドレスの使用を許可する場合は、このオプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="0343b-p104">**Use all configured IP addresses**. Select this option if you want to allow any IP address defined on the computer to be used.</span></span>

     > [!NOTE]
     > <span data-ttu-id="0343b-117">これは、IP version 6 (IPv6) 構成の推奨オプションです。</span><span class="sxs-lookup"><span data-stu-id="0343b-117">This is the recommended option for IP version 6 (IPv6) configurations.</span></span>

   - <span data-ttu-id="0343b-p105">[**サービスの使用を選択した IP アドレスに限定する**]。新しいサーバーで使用するアドレスを指定するには、このオプションを選択します。このオプションを選択した場合は、[**プライマリ IP アドレス**] に値を入力する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0343b-p105">**Limit service usage to selected IP addresses**. Select this option to specify a specific address to use on the new server. If you select this option, you must enter a value for **Primary IP address**.</span></span>

   - <span data-ttu-id="0343b-p106">[**プライマリ IP アドレス**]。公衆交換電話網 (PSTN) 以外のすべての通信でサーバーが使用する IP アドレスを入力します。入力する IP アドレスは、選択されているアドレスの種類の形式に一致している必要があります。</span><span class="sxs-lookup"><span data-stu-id="0343b-p106">**Primary IP address**. Enter an IP address that the server will use for all communications except public switched telephone network (PSTN). The IP address entered must match the format of the select address type.</span></span>

   - <span data-ttu-id="0343b-p107">[**PSTN IP アドレス**]。フロントエンド サーバーで仲介サーバーが共存する場合は、PSTN IP アドレスを定義します。このアドレスは、選択されているアドレスの種類の形式に一致している必要があります。</span><span class="sxs-lookup"><span data-stu-id="0343b-p107">**PSTN IP address**. Define a PSTN IP address when a Mediation Server is collocated on the Front End Server. This address must match the format of the selected address type.</span></span>

> [!NOTE]
> <span data-ttu-id="0343b-127">フロントエンドサーバーの PSTN IP アドレス構成 (またはその他の理由) をサポートするために、追加のネットワークインターフェイスカード (Nic) をインストールすることはサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="0343b-127">The installation of additional network interface cards (NICs) to support the PSTN IP address configuration (or for any other reason) on Front End Servers is not supported.</span></span> <span data-ttu-id="0343b-128">Skype for Business Server でサポートされる NIC 構成の詳細については、「 [Lync server 2013 用のサーバーハードウェアプラットフォーム](https://technet.microsoft.com/library/c964c1c0-0153-472b-88ad-a38866e0df0c.aspx)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0343b-128">For more information about supported NIC configurations for Skype for Business Server, see [Server hardware platforms for Lync Server 2013](https://technet.microsoft.com/library/c964c1c0-0153-472b-88ad-a38866e0df0c.aspx).</span></span>

## <a name="deploy-ip-address-types-on-a-mediation-server"></a><span data-ttu-id="0343b-129">仲介サーバーに IP アドレス タイプを展開する</span><span class="sxs-lookup"><span data-stu-id="0343b-129">Deploy IP address types on a Mediation Server</span></span>

<span data-ttu-id="0343b-130">トポロジビルダーを使用して、次の手順を実行して、仲介サーバーに IP アドレスの種類を展開します。</span><span class="sxs-lookup"><span data-stu-id="0343b-130">Using Topology Builder, perform the steps in the following procedure to deploy IP address types on a Mediation Server.</span></span>

### <a name="to-deploy-ip-address-types-on-a-mediation-server"></a><span data-ttu-id="0343b-131">仲介サーバーに IP アドレスの種類を展開するには</span><span class="sxs-lookup"><span data-stu-id="0343b-131">To deploy IP address types on a Mediation Server</span></span>

- <span data-ttu-id="0343b-132">[トポロジビルダー] の [**仲介プール**] で、プール内のサーバーを右クリックし、[**プロパティの編集**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="0343b-132">In Topology Builder, under **Mediation pools**, right-click the server within a pool, and then select **Edit Properties**.</span></span> <span data-ttu-id="0343b-133">(または、サーバーを選択し、[**アクション**] メニューの [**プロパティの編集**] をクリックします)。</span><span class="sxs-lookup"><span data-stu-id="0343b-133">(Alternatively, select the server, and then click **Edit Properties** from the **Action** menu.)</span></span>

- <span data-ttu-id="0343b-p110">[**プロパティの編集**] ダイアログ ボックスで、構成する IP アドレスの種類を選択します。デュアル スタック構成の場合は、次の図のように、[**IPv4 を有効にする**] および [**IPv6 を有効にする**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="0343b-p110">In the **Edit Properties** dialog box, select the IP address type that you want to configure. For a dual-stack configuration, select **Enable IPv4** and **Enable IPv6**, as shown in the following figure.</span></span>

   <span data-ttu-id="0343b-136">**仲介サーバー プールの [プロパティの編集] ダイアログ ボックス**</span><span class="sxs-lookup"><span data-stu-id="0343b-136">**Edit Properties dialog box for the Mediation Server pool**</span></span>

  - <span data-ttu-id="0343b-p111">[**すべての構成済み IP アドレスを使用する**]。コンピューター上で定義されているすべての IP アドレスの使用を許可する場合は、このオプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="0343b-p111">**Use all configured IP addresses**. Select this option if you want to allow any IP address defined on the computer to be used.</span></span>

    > [!NOTE]
    > <span data-ttu-id="0343b-139">これは、IP version 6 (IPv6) 構成の推奨オプションです。</span><span class="sxs-lookup"><span data-stu-id="0343b-139">This is the recommended option for IP version 6 (IPv6) configurations.</span></span>

  - <span data-ttu-id="0343b-p112">[**サービスの使用を、指定したアドレスに制限する**]。新しいサーバーで使用する特定のアドレスを指定する場合は、このオプションを選択します。このオプションを選択する場合は、プライマリ IP アドレスの値を入力する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0343b-p112">**Limit service usage to selected IP addresses**. Select this option to specify a specific address to use on the new server. If you select this option, you must enter a value for Primary IP address.</span></span>

  - <span data-ttu-id="0343b-p113">[**プライマリ IP アドレス**]。公衆交換電話網 (PSTN) 以外のすべての通信でサーバーが使用する IP アドレスを入力します。入力する IP アドレスは、選択されているアドレスの種類の形式に一致している必要があります。</span><span class="sxs-lookup"><span data-stu-id="0343b-p113">**Primary IP address**. Enter an IP address that the server will use for all communications except public switched telephone network (PSTN). The IP address entered must match the format of the select address type.</span></span>

  - <span data-ttu-id="0343b-p114">[**PSTN IP アドレス**]。フロントエンド サーバーで仲介サーバーが共存する場合は、PSTN IP アドレスを定義します。このアドレスは、選択されているアドレスの種類の形式に一致している必要があります。</span><span class="sxs-lookup"><span data-stu-id="0343b-p114">**PSTN IP address**. Define a PSTN IP address when a Mediation Server is collocated on the Front End Server. This address must match the format of the selected address type.</span></span>
> [!IMPORTANT]
> <span data-ttu-id="0343b-149">マイクロソフトでは、*専用*の仲介サーバー上の2つのネットワークカードのみをサポートしています。</span><span class="sxs-lookup"><span data-stu-id="0343b-149">We only support two network cards on *dedicated* Mediation Servers.</span></span> <span data-ttu-id="0343b-150">仲介 Sserver の役割がフロントエンドに併置されている場合は、デュアルネットワークカードはサポートされません。</span><span class="sxs-lookup"><span data-stu-id="0343b-150">If the Mediation Sserver role is collocated on the Front End, then dual network cards are not supported.</span></span> 

> [!NOTE]
> - <span data-ttu-id="0343b-151">Skype for Business Server 2015 でサポートされる NIC 構成の詳細については、「Skype for business [server 2015 のハードウェア](../requirements-for-your-environment/server-requirements.md#hardware-for-skype-for-business-server-2015)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0343b-151">For more information about supported NIC configurations for Skype for Business Server 2015, see [Hardware for Skype for Business Server 2015](../requirements-for-your-environment/server-requirements.md#hardware-for-skype-for-business-server-2015)</span></span>
> - <span data-ttu-id="0343b-152">Skype for Business Server 2019 でサポートされる NIC 構成の詳細については、「Skype for business [server 2019 のハードウェア](../../../SfBServer2019/plan/system-requirements.md#hardware-for-skype-for-business-server-2019)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0343b-152">For more information about supported NIC configurations for Skype for Business Server 2019, see [Hardware for Skype for Business Server 2019](../../../SfBServer2019/plan/system-requirements.md#hardware-for-skype-for-business-server-2019)</span></span>



## <a name="deploy-ip-address-types-on-an-edge-server"></a><span data-ttu-id="0343b-153">IP アドレスの種類をエッジ サーバーに展開する</span><span class="sxs-lookup"><span data-stu-id="0343b-153">Deploy IP address types on an Edge Server</span></span>

<span data-ttu-id="0343b-154">トポロジビルダーを使用して、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="0343b-154">Using Topology Builder, perform the following steps:</span></span>

### <a name="to-deploy-ip-address-types-on-an-edge-server"></a><span data-ttu-id="0343b-155">エッジ サーバー上に IP アドレスの種類を展開するには</span><span class="sxs-lookup"><span data-stu-id="0343b-155">To deploy IP address types on an Edge Server</span></span>

1. <span data-ttu-id="0343b-156">[トポロジビルダー] の [**エッジプール**] で、プール内のサーバーを右クリックし、[**プロパティの編集**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="0343b-156">In Topology Builder, under **Edge pools**, right-click the server within a pool, and then select **Edit Properties**.</span></span> <span data-ttu-id="0343b-157">(または、サーバーを選択し、[**アクション**] メニューの [**プロパティの編集**] をクリックします)。</span><span class="sxs-lookup"><span data-stu-id="0343b-157">(Alternatively, select the server, and then click **Edit Properties** from the **Action** menu.)</span></span>

2. <span data-ttu-id="0343b-158">[**プロパティの編集**] ウィンドウで、サポートする IP アドレス構成を選択します。</span><span class="sxs-lookup"><span data-stu-id="0343b-158">In the **Edit Properties** window, select the IP address configuration that you want to support.</span></span>

3. <span data-ttu-id="0343b-159">選択したアドレスの種類で、それぞれ適切な内部アドレスと外部アドレスを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0343b-159">For each address type that you select, you must supply appropriate internal and external addresses.</span></span>
