---
title: パイロット プール展開の DNS レコードの構成
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: パイロットプールを展開する前に、パイロットプールの DNS Host エントリを更新する必要があります。 この手順を完了するには、サーバーまたはドメインに、Domain Admins グループのメンバーまたは DnsAdmins グループのメンバーとしてログオンしている必要があります。
ms.openlocfilehash: 3b8485564f3ea7f37a06b5c4d13c9450ba0a2694
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34289624"
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
    

