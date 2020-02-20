---
title: 'Lync Server 2013: IP アドレスの種類をフロントエンドサーバーに展開する'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deploy IP address types on a Front End Server
ms:assetid: b6c8e0f9-ec8e-4a4e-a525-756f9cd6b9d0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205191(v=OCS.15)
ms:contentKeyID: 48185193
ms.date: 07/28/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f3be24a05cf75adfc999205bb306010ba43fa1d6
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "42150916"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="deploy-ip-address-types-on-a-front-end-server-for-lync-server-2013"></a>Lync Server 2013 のフロントエンドサーバーに IP アドレスタイプを展開する

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2016-07-28_

トポロジビルダーを使用して、次の手順を実行して、IP アドレスの種類をフロントエンドサーバーに展開します。

<div>

## <a name="to-deploy-ip-address-types-on-a-front-end-server"></a>IP アドレス タイプをフロントエンド サーバーに展開するには

1.  [**Enterprise Edition フロントエンドのプール**] で、プール内のサーバーを右クリックし、[**プロパティの編集**] を選択します (または、サーバーを選択し、[**アクション**] メニューの [**プロパティの編集**] をクリックします)。

2.  [**プロパティの編集**] ダイアログ ボックスで、構成する IP アドレス タイプを選択します。デュアル スタック構成の場合は、次の図のように、[**IPv4 を有効にする**] および [**IPv6 を有効にする**] を選択します。
    
    **フロントエンド サーバー プールの [プロパティの編集] ダイアログ ボックス**
    
    ![フロントエンドサーバーの [プロパティの編集] ダイアログボックス](images/JJ205191.737a9d71-c0bc-4a54-9608-9e028dacc814(OCS.15).png "フロントエンドサーバーの [プロパティの編集] ダイアログボックス")
    
      - [**すべての構成済み IP アドレスを使用する**]。コンピューター上で定義されているすべての IP アドレスの使用を許可する場合は、このオプションを選択します。
        
        <div>
        

        > [!NOTE]  
        > これは、IP version 6 (IPv6) 構成の推奨オプションです。

        
        </div>
    
      - [**サービスの使用を選択した IP アドレスに限定する**]。新しいサーバーで使用するアドレスを指定するには、このオプションを選択します。このオプションを選択した場合は、[**プライマリ IP アドレス**] に値を入力する必要があります。
    
      - [**プライマリ IP アドレス**]。公衆交換電話網 (PSTN) 以外のすべての通信でサーバーが使用する IP アドレスを入力します。入力する IP アドレスは、選択されているアドレス タイプの形式に一致している必要があります。
    
      - [**PSTN IP アドレス**]。 Lync Server 2013 の PSTN IP アドレス構成をサポートするための追加のネットワークインターフェイスカード (NIC) のインストールは、併置された仲介サーバーの役割ではサポートされていません。 Lync Server 2013 でサポートされている NIC 構成の詳細については、「 [Lync server 2013 のサーバーハードウェアプラットフォーム](lync-server-2013-server-hardware-platforms.md)」を参照してください。

</div>

</div>

<span> </span>

</div>

</div>

</div>

