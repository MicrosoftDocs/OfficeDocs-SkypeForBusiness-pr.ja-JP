---
title: IP アドレスの種類を構成Skype for Business
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 17e756c0-6652-4cd5-b185-4b25929e3a42
description: '概要: IP アドレスを実装する前に、以下の IP アドレスの種類に関する考慮事項をSkype for Business Server。'
ms.openlocfilehash: 076c0e0a3901a3c69a9c6dece73fda487cddfa8c
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/05/2022
ms.locfileid: "62390909"
---
# <a name="configure-ip-address-types-in-skype-for-business"></a>IP アドレスの種類を構成Skype for Business

**概要:** IP アドレスを実装する前に、以下の IP アドレスの種類に関する考慮事項をSkype for Business Server。

トポロジ ビルダーで構成するトポロジ設定を使用して、IP アドレスの種類を展開します。 ここでは、フロントエンド サーバー、仲介サーバー、エッジ サーバーに IP アドレスの種類を展開する方法について説明します。

## <a name="deploy-ip-address-types-on-a-front-end-server"></a>フロント エンド サーバーに IP アドレスの種類を展開する

トポロジ ビルダーを使用して、次の手順の手順を実行して、フロントエンド サーバーに IP アドレスの種類を展開します。

### <a name="to-deploy-ip-address-types-on-a-front-end-server"></a>IP アドレス タイプをフロントエンド サーバーに展開するには

1. [**Enterprise Edition フロントエンドのプール**] で、プール内のサーバーを右クリックし、[**プロパティの編集**] を選択します (または、サーバーを選択し、[**アクション**] メニューの [**プロパティの編集**] をクリックします)。

2. [**プロパティの編集**] ダイアログ ボックスで、構成する IP アドレス タイプを選択します。 デュアル スタック構成の場合は、[ **IPv4 を有効にする] と [IPv6** を **有効にする] を選択します**。

   **フロントエンド サーバー プールの [プロパティの編集] ダイアログ ボックス**

   - [**すべての構成済み IP アドレスを使用する**]。コンピューター上で定義されているすべての IP アドレスの使用を許可する場合は、このオプションを選択します。

     > [!NOTE]
     > これは、IP version 6 (IPv6) 構成の推奨オプションです。

   - [**サービスの使用を選択した IP アドレスに限定する**]。新しいサーバーで使用するアドレスを指定するには、このオプションを選択します。このオプションを選択した場合は、[**プライマリ IP アドレス**] に値を入力する必要があります。

   - [**プライマリ IP アドレス**]。公衆交換電話網 (PSTN) 以外のすべての通信でサーバーが使用する IP アドレスを入力します。入力する IP アドレスは、選択されているアドレス タイプの形式に一致している必要があります。

   - [**PSTN IP アドレス**]。フロントエンド サーバーで仲介サーバーが共存する場合は、PSTN IP アドレスを定義します。このアドレスは、選択されているアドレス タイプの形式に一致している必要があります。

> [!NOTE]
> フロント エンド サーバーでの PSTN IP アドレス構成 (または他の理由) をサポートする追加のネットワーク インターフェイス カード (NIC) のインストールはサポートされていません。 サポートされている NIC 構成の詳細については、「Skype for Business Server [Lync Server 2013 のサーバー](/previous-versions/office/lync-server-2013/lync-server-2013-server-hardware-platforms) ハードウェア プラットフォーム」を参照してください。

## <a name="deploy-ip-address-types-on-a-mediation-server"></a>仲介サーバーに IP アドレスの種類を展開する

トポロジ ビルダーを使用して、次の手順の手順を実行して、仲介サーバーに IP アドレスの種類を展開します。

### <a name="to-deploy-ip-address-types-on-a-mediation-server"></a>仲介サーバーに IP アドレス タイプを展開するには

- トポロジ ビルダーの [仲介プール] **で**、プール内のサーバーを右クリックし、[プロパティの編集] **を選択します**。 (または、サーバーを選択し、[操作] メニューの **[** プロパティの編集] **をクリック** します)。

- [**プロパティの編集**] ダイアログ ボックスで、構成する IP アドレス タイプを選択します。デュアル スタック構成の場合は、次の図のように、[**IPv4 を有効にする**] および [**IPv6 を有効にする**] を選択します。

   **仲介サーバー プールの [プロパティの編集] ダイアログ ボックス**

  - [**すべての構成済み IP アドレスを使用する**]。コンピューター上で定義されているすべての IP アドレスの使用を許可する場合は、このオプションを選択します。

    > [!NOTE]
    > これは、IP version 6 (IPv6) 構成の推奨オプションです。

  - [**サービスの使用を、指定したアドレスに制限する**]。新しいサーバーで使用する特定のアドレスを指定する場合は、このオプションを選択します。このオプションを選択する場合は、プライマリ IP アドレスの値を入力する必要があります。

  - [**プライマリ IP アドレス**]。公衆交換電話網 (PSTN) 以外のすべての通信でサーバーが使用する IP アドレスを入力します。入力する IP アドレスは、選択されているアドレス タイプの形式に一致している必要があります。

  - [**PSTN IP アドレス**]。フロントエンド サーバーで仲介サーバーが共存する場合は、PSTN IP アドレスを定義します。このアドレスは、選択されているアドレス タイプの形式に一致している必要があります。
> [!IMPORTANT]
> 専用の仲介サーバーでは、2 つの *ネットワーク カードのみを* サポートしています。 仲介 Sserver の役割がフロントエンドに共有されている場合、デュアル ネットワーク カードはサポートされません。 

> [!NOTE]
> - 2015 年 2015 年にサポートされる NIC 構成の詳細については、「Skype for Business Server ハードウェア [for Skype for Business Server 2015](../requirements-for-your-environment/server-requirements.md#hardware-for-skype-for-business-server-2015)」を参照してください。
> - 2019 年 2019 年にサポートされる Skype for Business Server NIC 構成の詳細については、「ハードウェア [for Skype for Business Server 2019」を参照してください。](../../../SfBServer2019/plan/system-requirements.md#hardware-for-skype-for-business-server-2019)



## <a name="deploy-ip-address-types-on-an-edge-server"></a>エッジ サーバーに IP アドレスの種類を展開する

トポロジ ビルダーを使用して、次の手順を実行します。

### <a name="to-deploy-ip-address-types-on-an-edge-server"></a>エッジ サーバー上に IP アドレスの種類を展開するには

1. トポロジ ビルダーの [エッジ プール **] で**、プール内のサーバーを右クリックし、[プロパティの編集] **を選択します**。 (または、サーバーを選択し、[操作] メニューの **[** プロパティの編集] **をクリック** します)。

2. [**プロパティの編集**] ウィンドウで、サポートする IP アドレス構成を選択します。

3. 選択したアドレスの種類のそれぞれで、適切な内部アドレスと外部アドレスを指定する必要があります。