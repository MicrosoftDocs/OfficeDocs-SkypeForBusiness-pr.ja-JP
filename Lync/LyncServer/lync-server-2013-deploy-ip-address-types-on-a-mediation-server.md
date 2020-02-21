---
title: 'Lync Server 2013: 仲介サーバーに IP アドレスタイプを展開する'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deploy IP address types on a Mediation Server
ms:assetid: 689ebed5-96ee-4cd4-b7ae-ee2a86a1d9b3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204964(v=OCS.15)
ms:contentKeyID: 48184376
ms.date: 07/28/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7705da8beee8f6ee45d74fbdbb6eb03180234a47
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2020
ms.locfileid: "42179664"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="deploy-ip-address-types-on-a-mediation-server-for-lync-server-2013"></a>Lync Server 2013 の仲介サーバーに IP アドレスタイプを展開する

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2016-07-28_

トポロジビルダーを使用して、次の手順を実行し、仲介サーバーに IP アドレスの種類を展開します。

<div>

## <a name="to-deploy-ip-address-types-on-a-mediation-server"></a>仲介サーバーに IP アドレス タイプを展開するには

  - トポロジビルダーの [**仲介プール**] で、プール内のサーバーを右クリックし、[**プロパティの編集**] を選択します。 または、サーバーを選択し、[**アクション**] メニューの [**プロパティの編集**] をクリックします。

  - [**プロパティの編集**] ダイアログ ボックスで、構成する IP アドレス タイプを選択します。デュアル スタック構成の場合は、次の図のように、[**IPv4 を有効にする**] および [**IPv6 を有効にする**] を選択します。
    
    **仲介サーバー プールの [プロパティの編集] ダイアログ ボックス**
    
    ![[Lync Server の全般プロパティ] ページ (FQDN 付き)](images/JJ204964.4e650aca-dbff-4a86-b10d-f0162c032539(OCS.15).png "[Lync Server の全般プロパティ] ページ (FQDN 付き)")
    
      - [**すべての構成済み IP アドレスを使用する**]。コンピューター上で定義されているすべての IP アドレスの使用を許可する場合は、このオプションを選択します。
        
        <div>
        

        > [!NOTE]  
        > これは、IP version 6 (IPv6) 構成の推奨オプションです。

        
        </div>
    
      - [**サービスの使用を、指定したアドレスに制限する**]。新しいサーバーで使用する特定のアドレスを指定する場合は、このオプションを選択します。このオプションを選択する場合は、プライマリ IP アドレスの値を入力する必要があります。
    
      - [**プライマリ IP アドレス**]。公衆交換電話網 (PSTN) 以外のすべての通信でサーバーが使用する IP アドレスを入力します。入力する IP アドレスは、選択されているアドレス タイプの形式に一致している必要があります。
    
      - [**PSTN IP アドレス**]。 仲介サーバーがスタンドアロンの場合は、PSTN IP アドレスを定義します。 このアドレスは、選択されているアドレス タイプの形式に一致している必要があります。
        
        <div>
        

        > [!NOTE]  
        > Lync Server 2013 の PSTN IP アドレス構成をサポートするための追加のネットワークインターフェイスカード (NIC) のインストールは、併置された仲介サーバーの役割ではサポートされていません。 Lync Server 2013 でサポートされている NIC 構成の詳細については、「 <A href="lync-server-2013-server-hardware-platforms.md">Lync server 2013 のサーバーハードウェアプラットフォーム</A>」を参照してください。

        
        </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

