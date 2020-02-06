---
title: パイロット プール展開の DNS レコードの構成
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: パイロットプールを展開する前に、パイロットプールの DNS Host エントリを更新する必要があります。 この手順を完了するには、サーバーまたはドメインに、Domain Admins グループのメンバーまたは DnsAdmins グループのメンバーとしてログオンしている必要があります。
ms.openlocfilehash: 94e5047dc82b0ddb55b03ad5c466011878c05ae7
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41813855"
---
# <a name="configure-dns-records-for-pilot-pool-deployment"></a>パイロット プール展開の DNS レコードの構成

パイロットプールを展開する前に、パイロットプールの DNS Host A エントリを更新する必要があります。 この手順を完了するには、サーバーまたはドメインに、Domain Admins グループのメンバーまたは DnsAdmins グループのメンバーとしてログオンしている必要があります。
  
### <a name="to-configure-dns-host-a-records"></a>DNS ホスト A レコードを構成するには

1. ドメインネームシステム (DNS) サーバーで、[**スタート**] をクリックし、[**管理ツール**]、[ **DNS**] の順にクリックします。
    
2. ドメインのコンソールツリーで [**前方参照ゾーン**] を展開し、Skype For business Server 2019 がインストールされているドメインを右クリックします。
    
3. [**新しいホスト (A または AAAA)**] をクリックします。
    
4. [**名前**] をクリックし、Skype For business Server 2019 プールのホスト名を入力します (ドメイン名は、レコードが定義されていて、A レコードの一部として入力する必要はありません)。
    
5. [ **Ip アドレス**] をクリックして、フロントエンドプールの ip アドレスを入力します。
    
6. [**ホストの追加**] をクリックし、[ **OK**] をクリックします。 
    
7. 完了したら、[**完了**] をクリックします。
    

