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
# <a name="configure-ip-address-types-in-skype-for-business"></a>Skype for Business で IP アドレスの種類を構成する

**概要:** Skype for Business Server を実装する前に、以下の IP アドレスの種類に関する考慮事項を確認してください。

IP アドレスの種類は、トポロジ ビルダーで構成したトポロジ設定を使用して展開します。 このセクションでは、フロントエンド サーバー、仲介サーバー、およびエッジ サーバーに IP アドレスの種類を展開する方法について説明します。

## <a name="deploy-ip-address-types-on-a-front-end-server"></a>フロントエンド サーバーに IP アドレスの種類を展開する

トポロジ ビルダーを使用して、以下の手順を実行して、IP アドレスの種類をフロントエンド サーバーに展開します。

### <a name="to-deploy-ip-address-types-on-a-front-end-server"></a>IP アドレス タイプをフロントエンド サーバーに展開するには

1. [**Enterprise Edition フロントエンドのプール**] で、プール内のサーバーを右クリックし、[**プロパティの編集**] を選択します (または、サーバーを選択し、[**アクション**] メニューの [**プロパティの編集**] をクリックします)。

2. [**プロパティの編集**] ダイアログ ボックスで、構成する IP アドレス タイプを選択します。 デュアル スタック構成の場合は **、[IPv4** を有効にして IPv6 を有効にする **] を選択します**。

   **フロントエンド サーバー プールの [プロパティの編集] ダイアログ ボックス**

   - [**すべての構成済み IP アドレスを使用する**]。コンピューター上で定義されているすべての IP アドレスの使用を許可する場合は、このオプションを選択します。

     > [!NOTE]
     > これは、IP version 6 (IPv6) 構成の推奨オプションです。

   - [**サービスの使用を選択した IP アドレスに限定する**]。新しいサーバーで使用するアドレスを指定するには、このオプションを選択します。このオプションを選択した場合は、[**プライマリ IP アドレス**] に値を入力する必要があります。

   - [**プライマリ IP アドレス**]。公衆交換電話網 (PSTN) 以外のすべての通信でサーバーが使用する IP アドレスを入力します。入力する IP アドレスは、選択されているアドレス タイプの形式に一致している必要があります。

   - [**PSTN IP アドレス**]。フロントエンド サーバーで仲介サーバーが共存する場合は、PSTN IP アドレスを定義します。このアドレスは、選択されているアドレス タイプの形式に一致している必要があります。

> [!NOTE]
> フロント エンド サーバーでの PSTN IP アドレス構成 (または何らかの理由で) をサポートする追加のネットワーク インターフェイス カード (NIC) のインストールはサポートされていません。 Skype for Business Server でサポートされる NIC 構成の詳細については [、Lync Server 2013](https://technet.microsoft.com/library/c964c1c0-0153-472b-88ad-a38866e0df0c.aspx)のサーバー ハードウェア プラットフォームを参照してください。

## <a name="deploy-ip-address-types-on-a-mediation-server"></a>仲介サーバーに IP アドレスの種類を展開する

トポロジ ビルダーを使用して、以下の手順を実行して、仲介サーバーに IP アドレスの種類を展開します。

### <a name="to-deploy-ip-address-types-on-a-mediation-server"></a>仲介サーバーに IP アドレス タイプを展開するには

- トポロジ ビルダーの仲介プール **で**、プール内のサーバーを右クリックし、[プロパティの編集] **を選択します**。 (または、サーバーを選択し、[操作] メニューの **[プロパティの** 編集 **] をクリック** します)。

- [**プロパティの編集**] ダイアログ ボックスで、構成する IP アドレス タイプを選択します。デュアル スタック構成の場合は、次の図のように、[**IPv4 を有効にする**] および [**IPv6 を有効にする**] を選択します。

   **仲介サーバー プールの [プロパティの編集] ダイアログ ボックス**

  - [**すべての構成済み IP アドレスを使用する**]。コンピューター上で定義されているすべての IP アドレスの使用を許可する場合は、このオプションを選択します。

    > [!NOTE]
    > これは、IP version 6 (IPv6) 構成の推奨オプションです。

  - [**サービスの使用を、指定したアドレスに制限する**]。新しいサーバーで使用する特定のアドレスを指定する場合は、このオプションを選択します。このオプションを選択する場合は、プライマリ IP アドレスの値を入力する必要があります。

  - [**プライマリ IP アドレス**]。公衆交換電話網 (PSTN) 以外のすべての通信でサーバーが使用する IP アドレスを入力します。入力する IP アドレスは、選択されているアドレス タイプの形式に一致している必要があります。

  - [**PSTN IP アドレス**]。フロントエンド サーバーで仲介サーバーが共存する場合は、PSTN IP アドレスを定義します。このアドレスは、選択されているアドレス タイプの形式に一致している必要があります。
> [!IMPORTANT]
> 専用の仲介サーバーでサポートされるネットワーク カード *は 2* つのみです。 仲介 Sserver の役割がフロントエンドに一重に展開されている場合、デュアル ネットワーク カードはサポートされません。 

> [!NOTE]
> - Skype for Business Server 2015 でサポートされる NIC 構成の詳細については[、「Hardware for Skype for Business Server 2015」](../requirements-for-your-environment/server-requirements.md#hardware-for-skype-for-business-server-2015)を参照してください。
> - Skype for Business Server 2019 でサポートされる NIC 構成の詳細については[、「Hardware for Skype for Business Server 2019」](../../../SfBServer2019/plan/system-requirements.md#hardware-for-skype-for-business-server-2019)を参照してください。



## <a name="deploy-ip-address-types-on-an-edge-server"></a>IP アドレスの種類をエッジ サーバーに展開する

トポロジ ビルダーを使用して、次の手順を実行します。

### <a name="to-deploy-ip-address-types-on-an-edge-server"></a>エッジ サーバー上に IP アドレスの種類を展開するには

1. トポロジ ビルダーのエッジ プール **で**、プール内のサーバーを右クリックし、[プロパティの編集] **を選択します**。 (または、サーバーを選択し、[操作] メニューの **[プロパティの** 編集 **] をクリック** します)。

2. [**プロパティの編集**] ウィンドウで、サポートする IP アドレス構成を選択します。

3. 選択したアドレスの種類のそれぞれで、適切な内部アドレスと外部アドレスを指定する必要があります。
