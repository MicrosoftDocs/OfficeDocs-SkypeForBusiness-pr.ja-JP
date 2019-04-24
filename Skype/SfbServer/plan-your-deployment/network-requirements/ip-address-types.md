---
title: Skype for Business での IP アドレスの種類の構成
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 17e756c0-6652-4cd5-b185-4b25929e3a42
description: '概要: は、Skype をビジネスのサーバーを実装する前に以下の IP アドレス タイプの考慮事項を確認します。'
ms.openlocfilehash: 4ebf8c3329358e526f86dd90eb4cbc0340d06606
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "32206297"
---
# <a name="configure-ip-address-types-in-skype-for-business"></a><span data-ttu-id="1a8b7-103">Skype for Business での IP アドレスの種類の構成</span><span class="sxs-lookup"><span data-stu-id="1a8b7-103">Configure IP address types in Skype for Business</span></span>

<span data-ttu-id="1a8b7-104">**の概要:** Skype をビジネスのサーバーを実装する前に以下の IP アドレス タイプの考慮事項を確認します。</span><span class="sxs-lookup"><span data-stu-id="1a8b7-104">**Summary:** Review the IP Address type considerations below before implementing Skype for Business Server.</span></span>

<span data-ttu-id="1a8b7-105">IP アドレスの種類を展開するには、トポロジ ビルダーでトポロジ設定を使用します。</span><span class="sxs-lookup"><span data-stu-id="1a8b7-105">You deploy IP address types by using topology settings that you configure in Topology Builder.</span></span> <span data-ttu-id="1a8b7-106">このセクションでは、フロント エンド サーバー、仲介サーバー、およびエッジ トランスポート サーバーの IP アドレスの種類を展開する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="1a8b7-106">This section describes how to deploy IP address types on Front End Servers, Mediation Servers, and Edge Servers.</span></span>

## <a name="deploy-ip-address-types-on-a-front-end-server"></a><span data-ttu-id="1a8b7-107">IP アドレス タイプをフロント エンド サーバーに展開する</span><span class="sxs-lookup"><span data-stu-id="1a8b7-107">Deploy IP address types on a Front End Server</span></span>

<span data-ttu-id="1a8b7-108">トポロジ ビルダーを使用すると、サーバーをフロント エンド サーバーの IP アドレスの種類を展開するのには次の手順で手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="1a8b7-108">Using Topology Builder, perform the steps in the following procedure to deploy IP address types on a Front End Server.</span></span>

### <a name="to-deploy-ip-address-types-on-a-front-end-server"></a><span data-ttu-id="1a8b7-109">IP アドレスの種類をフロントエンド サーバーに展開するには</span><span class="sxs-lookup"><span data-stu-id="1a8b7-109">To deploy IP address types on a Front End Server</span></span>

1. <span data-ttu-id="1a8b7-p102">[**Enterprise Edition フロントエンドのプール**] で、プール内のサーバーを右クリックし、[**プロパティの編集**] を選択します (または、サーバーを選択し、[**アクション**] メニューの [**プロパティの編集**] をクリックします)。</span><span class="sxs-lookup"><span data-stu-id="1a8b7-p102">Under **Enterprise Edition Front End pools**, right-click the server within a pool, and then select **Edit Properties**. (Alternatively, select the server, and then click **Edit Properties** from the **Action** menu.)</span></span>

2. <span data-ttu-id="1a8b7-112">[**プロパティの編集**] ダイアログ ボックスで、構成する IP アドレスの種類を選択します。</span><span class="sxs-lookup"><span data-stu-id="1a8b7-112">In the **Edit Properties** dialog box, select the IP address type that you want to configure.</span></span> <span data-ttu-id="1a8b7-113">デュアル ・ スタック構成では、**有効にする IPv4**と**IPv6 を有効にする**を選択します。</span><span class="sxs-lookup"><span data-stu-id="1a8b7-113">For a dual-stack configuration, select **Enable IPv4** and **Enable IPv6**.</span></span>

   <span data-ttu-id="1a8b7-114">**フロントエンド サーバー プールの [プロパティの編集] ダイアログ ボックス**</span><span class="sxs-lookup"><span data-stu-id="1a8b7-114">**Edit Properties dialog box for the Front End Server pool**</span></span>

   - <span data-ttu-id="1a8b7-p104">[**すべての構成済み IP アドレスを使用する**]。コンピューター上で定義されているすべての IP アドレスの使用を許可する場合は、このオプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="1a8b7-p104">**Use all configured IP addresses**. Select this option if you want to allow any IP address defined on the computer to be used.</span></span>

     > [!NOTE]
     > <span data-ttu-id="1a8b7-117">これは、IP version 6 (IPv6) 構成の推奨オプションです。</span><span class="sxs-lookup"><span data-stu-id="1a8b7-117">This is the recommended option for IP version 6 (IPv6) configurations.</span></span>

   - <span data-ttu-id="1a8b7-p105">[**サービスの使用を選択した IP アドレスに限定する**]。新しいサーバーで使用するアドレスを指定するには、このオプションを選択します。このオプションを選択した場合は、[**プライマリ IP アドレス**] に値を入力する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1a8b7-p105">**Limit service usage to selected IP addresses**. Select this option to specify a specific address to use on the new server. If you select this option, you must enter a value for **Primary IP address**.</span></span>

   - <span data-ttu-id="1a8b7-p106">[**プライマリ IP アドレス**]。公衆交換電話網 (PSTN) 以外のすべての通信でサーバーが使用する IP アドレスを入力します。入力する IP アドレスは、選択されているアドレスの種類の形式に一致している必要があります。</span><span class="sxs-lookup"><span data-stu-id="1a8b7-p106">**Primary IP address**. Enter an IP address that the server will use for all communications except public switched telephone network (PSTN). The IP address entered must match the format of the select address type.</span></span>

   - <span data-ttu-id="1a8b7-p107">[**PSTN IP アドレス**]。フロントエンド サーバーで仲介サーバーが共存する場合は、PSTN IP アドレスを定義します。このアドレスは、選択されているアドレスの種類の形式に一致している必要があります。</span><span class="sxs-lookup"><span data-stu-id="1a8b7-p107">**PSTN IP address**. Define a PSTN IP address when a Mediation Server is collocated on the Front End Server. This address must match the format of the selected address type.</span></span>

> [!NOTE]
> <span data-ttu-id="1a8b7-127">インストールの追加のネットワーク インターフェイス カード (Nic) が PSTN の IP アドレスの構成をサポートするために (またはその他の何らかの理由で) フロント エンド サーバーではサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="1a8b7-127">The installation of additional network interface cards (NICs) to support the PSTN IP address configuration (or for any other reason) on Front End Servers is not supported.</span></span> <span data-ttu-id="1a8b7-128">ビジネス サーバーの Skype のサポートされている NIC 構成の詳細については、 [Lync Server 2013 のサーバー ハードウェア プラットフォーム](https://technet.microsoft.com/library/c964c1c0-0153-472b-88ad-a38866e0df0c.aspx)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1a8b7-128">For more information about supported NIC configurations for Skype for Business Server, see [Server hardware platforms for Lync Server 2013](https://technet.microsoft.com/library/c964c1c0-0153-472b-88ad-a38866e0df0c.aspx).</span></span>

## <a name="deploy-ip-address-types-on-a-mediation-server"></a><span data-ttu-id="1a8b7-129">仲介サーバーに IP アドレス タイプを展開する</span><span class="sxs-lookup"><span data-stu-id="1a8b7-129">Deploy IP address types on a Mediation Server</span></span>

<span data-ttu-id="1a8b7-130">トポロジ ビルダーを使用すると、仲介サーバーの IP アドレスの種類を展開するのには次の手順で手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="1a8b7-130">Using Topology Builder, perform the steps in the following procedure to deploy IP address types on a Mediation Server.</span></span>

### <a name="to-deploy-ip-address-types-on-a-mediation-server"></a><span data-ttu-id="1a8b7-131">仲介サーバーに IP アドレスの種類を展開するには</span><span class="sxs-lookup"><span data-stu-id="1a8b7-131">To deploy IP address types on a Mediation Server</span></span>

- <span data-ttu-id="1a8b7-132">トポロジ ビルダーで、[**仲介プール**プール内でサーバーを右クリックし、**プロパティの編集**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="1a8b7-132">In Topology Builder, under **Mediation pools**, right-click the server within a pool, and then select **Edit Properties**.</span></span> <span data-ttu-id="1a8b7-133">(または、サーバーを選択し、 **[操作**] メニューから **[プロパティの編集**] をクリックして)。</span><span class="sxs-lookup"><span data-stu-id="1a8b7-133">(Alternatively, select the server, and then click **Edit Properties** from the **Action** menu.)</span></span>

- <span data-ttu-id="1a8b7-p110">[**プロパティの編集**] ダイアログ ボックスで、構成する IP アドレスの種類を選択します。デュアル スタック構成の場合は、次の図のように、[**IPv4 を有効にする**] および [**IPv6 を有効にする**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="1a8b7-p110">In the **Edit Properties** dialog box, select the IP address type that you want to configure. For a dual-stack configuration, select **Enable IPv4** and **Enable IPv6**, as shown in the following figure.</span></span>

   <span data-ttu-id="1a8b7-136">**仲介サーバー プールの [プロパティの編集] ダイアログ ボックス**</span><span class="sxs-lookup"><span data-stu-id="1a8b7-136">**Edit Properties dialog box for the Mediation Server pool**</span></span>

  - <span data-ttu-id="1a8b7-p111">[**すべての構成済み IP アドレスを使用する**]。コンピューター上で定義されているすべての IP アドレスの使用を許可する場合は、このオプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="1a8b7-p111">**Use all configured IP addresses**. Select this option if you want to allow any IP address defined on the computer to be used.</span></span>

    > [!NOTE]
    > <span data-ttu-id="1a8b7-139">これは、IP version 6 (IPv6) 構成の推奨オプションです。</span><span class="sxs-lookup"><span data-stu-id="1a8b7-139">This is the recommended option for IP version 6 (IPv6) configurations.</span></span>

  - <span data-ttu-id="1a8b7-p112">[**サービスの使用を、指定したアドレスに制限する**]。新しいサーバーで使用する特定のアドレスを指定する場合は、このオプションを選択します。このオプションを選択する場合は、プライマリ IP アドレスの値を入力する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1a8b7-p112">**Limit service usage to selected IP addresses**. Select this option to specify a specific address to use on the new server. If you select this option, you must enter a value for Primary IP address.</span></span>

  - <span data-ttu-id="1a8b7-p113">[**プライマリ IP アドレス**]。公衆交換電話網 (PSTN) 以外のすべての通信でサーバーが使用する IP アドレスを入力します。入力する IP アドレスは、選択されているアドレスの種類の形式に一致している必要があります。</span><span class="sxs-lookup"><span data-stu-id="1a8b7-p113">**Primary IP address**. Enter an IP address that the server will use for all communications except public switched telephone network (PSTN). The IP address entered must match the format of the select address type.</span></span>

  - <span data-ttu-id="1a8b7-p114">[**PSTN IP アドレス**]。フロントエンド サーバーで仲介サーバーが共存する場合は、PSTN IP アドレスを定義します。このアドレスは、選択されているアドレスの種類の形式に一致している必要があります。</span><span class="sxs-lookup"><span data-stu-id="1a8b7-p114">**PSTN IP address**. Define a PSTN IP address when a Mediation Server is collocated on the Front End Server. This address must match the format of the selected address type.</span></span>
> [!IMPORTANT]
> <span data-ttu-id="1a8b7-149">だけ*専用*仲介サーバーに 2 つのネットワーク カードがサポートします。</span><span class="sxs-lookup"><span data-stu-id="1a8b7-149">We only support two network cards on *dedicated* Mediation Servers.</span></span> <span data-ttu-id="1a8b7-150">仲介サーバの役割がフロント エンドに併設されている場合は、2 つのネットワーク カードはサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="1a8b7-150">If the Mediation Sserver role is collocated on the Front End, then dual network cards are not supported.</span></span> 

> [!NOTE]
> - <span data-ttu-id="1a8b7-151">ビジネス サーバー 2015 の Skype のサポートされている NIC 構成の詳細については、[ビジネス サーバー 2015 の Skype のハードウェア](../requirements-for-your-environment/server-requirements.md#hardware-for-skype-for-business-server-2015)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1a8b7-151">For more information about supported NIC configurations for Skype for Business Server 2015, see [Hardware for Skype for Business Server 2015](../requirements-for-your-environment/server-requirements.md#hardware-for-skype-for-business-server-2015)</span></span>
> - <span data-ttu-id="1a8b7-152">ビジネス サーバー 2019 の Skype のサポートされている NIC 構成の詳細については、[ビジネス サーバー 2019 の Skype のハードウェア](../../../SfBServer2019/plan/system-requirements.md#hardware-for-skype-for-business-server-2019)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1a8b7-152">For more information about supported NIC configurations for Skype for Business Server 2019, see [Hardware for Skype for Business Server 2019](../../../SfBServer2019/plan/system-requirements.md#hardware-for-skype-for-business-server-2019)</span></span>



## <a name="deploy-ip-address-types-on-an-edge-server"></a><span data-ttu-id="1a8b7-153">IP アドレスの種類をエッジ サーバーに展開する</span><span class="sxs-lookup"><span data-stu-id="1a8b7-153">Deploy IP address types on an Edge Server</span></span>

<span data-ttu-id="1a8b7-154">トポロジ ビルダーを使用すると、次の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="1a8b7-154">Using Topology Builder, perform the following steps:</span></span>

### <a name="to-deploy-ip-address-types-on-an-edge-server"></a><span data-ttu-id="1a8b7-155">エッジ サーバー上に IP アドレスの種類を展開するには</span><span class="sxs-lookup"><span data-stu-id="1a8b7-155">To deploy IP address types on an Edge Server</span></span>

1. <span data-ttu-id="1a8b7-156">トポロジ ビルダーで、[**エッジ プール**、プール内でサーバーを右クリックし、**プロパティの編集**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="1a8b7-156">In Topology Builder, under **Edge pools**, right-click the server within a pool, and then select **Edit Properties**.</span></span> <span data-ttu-id="1a8b7-157">(または、サーバーを選択し、 **[操作**] メニューから **[プロパティの編集**] をクリックして)。</span><span class="sxs-lookup"><span data-stu-id="1a8b7-157">(Alternatively, select the server, and then click **Edit Properties** from the **Action** menu.)</span></span>

2. <span data-ttu-id="1a8b7-158">[**プロパティの編集**] ウィンドウで、サポートする IP アドレス構成を選択します。</span><span class="sxs-lookup"><span data-stu-id="1a8b7-158">In the **Edit Properties** window, select the IP address configuration that you want to support.</span></span>

3. <span data-ttu-id="1a8b7-159">選択したアドレスの種類で、それぞれ適切な内部アドレスと外部アドレスを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1a8b7-159">For each address type that you select, you must supply appropriate internal and external addresses.</span></span>
