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
# <a name="configure-ip-address-types-in-skype-for-business"></a>Skype for Business での IP アドレスの種類の構成

**概要:** Skype for Business Server を実装する前に、次の IP アドレスの種類に関する考慮事項を確認してください。

IP アドレスの種類を展開するには、トポロジビルダーで構成したトポロジ設定を使用します。 このセクションでは、フロントエンドサーバー、仲介サーバー、およびエッジサーバーに IP アドレスの種類を展開する方法について説明します。

## <a name="deploy-ip-address-types-on-a-front-end-server"></a>IP アドレス タイプをフロント エンド サーバーに展開する

トポロジビルダーを使用して、次の手順を実行して、フロントエンドサーバーに IP アドレスの種類を展開します。

### <a name="to-deploy-ip-address-types-on-a-front-end-server"></a>IP アドレスの種類をフロントエンド サーバーに展開するには

1. [**Enterprise Edition フロントエンドのプール**] で、プール内のサーバーを右クリックし、[**プロパティの編集**] を選択します (または、サーバーを選択し、[**アクション**] メニューの [**プロパティの編集**] をクリックします)。

2. [**プロパティの編集**] ダイアログ ボックスで、構成する IP アドレスの種類を選択します。 デュアルスタック構成の場合は、[ **IPv4 を有効に**し、 **IPv6 を有効**にする] を選択します。

   **フロントエンド サーバー プールの [プロパティの編集] ダイアログ ボックス**

   - [**すべての構成済み IP アドレスを使用する**]。コンピューター上で定義されているすべての IP アドレスの使用を許可する場合は、このオプションを選択します。

     > [!NOTE]
     > これは、IP version 6 (IPv6) 構成の推奨オプションです。

   - [**サービスの使用を選択した IP アドレスに限定する**]。新しいサーバーで使用するアドレスを指定するには、このオプションを選択します。このオプションを選択した場合は、[**プライマリ IP アドレス**] に値を入力する必要があります。

   - [**プライマリ IP アドレス**]。公衆交換電話網 (PSTN) 以外のすべての通信でサーバーが使用する IP アドレスを入力します。入力する IP アドレスは、選択されているアドレスの種類の形式に一致している必要があります。

   - [**PSTN IP アドレス**]。フロントエンド サーバーで仲介サーバーが共存する場合は、PSTN IP アドレスを定義します。このアドレスは、選択されているアドレスの種類の形式に一致している必要があります。

> [!NOTE]
> フロントエンドサーバーの PSTN IP アドレス構成 (またはその他の理由) をサポートするために、追加のネットワークインターフェイスカード (Nic) をインストールすることはサポートされていません。 Skype for Business Server でサポートされる NIC 構成の詳細については、「 [Lync server 2013 用のサーバーハードウェアプラットフォーム](https://technet.microsoft.com/library/c964c1c0-0153-472b-88ad-a38866e0df0c.aspx)」を参照してください。

## <a name="deploy-ip-address-types-on-a-mediation-server"></a>仲介サーバーに IP アドレス タイプを展開する

トポロジビルダーを使用して、次の手順を実行して、仲介サーバーに IP アドレスの種類を展開します。

### <a name="to-deploy-ip-address-types-on-a-mediation-server"></a>仲介サーバーに IP アドレスの種類を展開するには

- [トポロジビルダー] の [**仲介プール**] で、プール内のサーバーを右クリックし、[**プロパティの編集**] を選択します。 (または、サーバーを選択し、[**アクション**] メニューの [**プロパティの編集**] をクリックします)。

- [**プロパティの編集**] ダイアログ ボックスで、構成する IP アドレスの種類を選択します。デュアル スタック構成の場合は、次の図のように、[**IPv4 を有効にする**] および [**IPv6 を有効にする**] を選択します。

   **仲介サーバー プールの [プロパティの編集] ダイアログ ボックス**

  - [**すべての構成済み IP アドレスを使用する**]。コンピューター上で定義されているすべての IP アドレスの使用を許可する場合は、このオプションを選択します。

    > [!NOTE]
    > これは、IP version 6 (IPv6) 構成の推奨オプションです。

  - [**サービスの使用を、指定したアドレスに制限する**]。新しいサーバーで使用する特定のアドレスを指定する場合は、このオプションを選択します。このオプションを選択する場合は、プライマリ IP アドレスの値を入力する必要があります。

  - [**プライマリ IP アドレス**]。公衆交換電話網 (PSTN) 以外のすべての通信でサーバーが使用する IP アドレスを入力します。入力する IP アドレスは、選択されているアドレスの種類の形式に一致している必要があります。

  - [**PSTN IP アドレス**]。フロントエンド サーバーで仲介サーバーが共存する場合は、PSTN IP アドレスを定義します。このアドレスは、選択されているアドレスの種類の形式に一致している必要があります。
> [!IMPORTANT]
> マイクロソフトでは、*専用*の仲介サーバー上の2つのネットワークカードのみをサポートしています。 仲介 Sserver の役割がフロントエンドに併置されている場合は、デュアルネットワークカードはサポートされません。 

> [!NOTE]
> - Skype for Business Server 2015 でサポートされる NIC 構成の詳細については、「Skype for business [server 2015 のハードウェア](../requirements-for-your-environment/server-requirements.md#hardware-for-skype-for-business-server-2015)」を参照してください。
> - Skype for Business Server 2019 でサポートされる NIC 構成の詳細については、「Skype for business [server 2019 のハードウェア](../../../SfBServer2019/plan/system-requirements.md#hardware-for-skype-for-business-server-2019)」を参照してください。



## <a name="deploy-ip-address-types-on-an-edge-server"></a>IP アドレスの種類をエッジ サーバーに展開する

トポロジビルダーを使用して、次の手順を実行します。

### <a name="to-deploy-ip-address-types-on-an-edge-server"></a>エッジ サーバー上に IP アドレスの種類を展開するには

1. [トポロジビルダー] の [**エッジプール**] で、プール内のサーバーを右クリックし、[**プロパティの編集**] を選択します。 (または、サーバーを選択し、[**アクション**] メニューの [**プロパティの編集**] をクリックします)。

2. [**プロパティの編集**] ウィンドウで、サポートする IP アドレス構成を選択します。

3. 選択したアドレスの種類で、それぞれ適切な内部アドレスと外部アドレスを指定する必要があります。
