---
title: パイロット プール展開の DNS レコードの構成
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
description: パイロット プールを展開する前に、パイロット プールの DNS ホスト A エントリを更新する必要があります。 この手順を正常に完了するには、Domain Admins グループまたは DnsAdmins グループのメンバーとしてサーバーまたはドメインにログオンしている必要があります。
ms.openlocfilehash: e77a85d84debadc19e52cb2d195ac86f5b3e6055
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/26/2021
ms.locfileid: "58588059"
---
# <a name="configure-dns-records-for-pilot-pool-deployment"></a>パイロット プール展開の DNS レコードの構成

パイロット プールを展開する前に、パイロット プールの DNS ホスト A エントリを更新する必要があります。 この手順を正常に完了するには、Domain Admins グループまたは DnsAdmins グループのメンバーとしてサーバーまたはドメインにログオンしている必要があります。
  
### <a name="to-configure-dns-host-a-records"></a>DNS ホスト A レコードを構成するには

1. ドメイン ネーム システム (DNS) サーバーで、[**スタート**]、[**管理ツール**]、および [**DNS**] の順にクリックします。
    
2. ドメインのコンソール ツリーで、[前方参照ゾーン] を展開し、2019 年 2019 年にインストールされるドメインSkype for Business Server右クリックします。
    
3. [**新しいホスト (A または AAAA)**] をクリックします。
    
4. [**名前**] をクリックし、Skype for Business Server 2019 プールのホスト名を入力します (ドメイン名は、レコードが定義されている領域と見なされ、A レコードの一部として入力する必要があります)。
    
5. [IP **アドレス]** をクリックし、フロントエンド プールの IP アドレスを入力します。
    
6. [**ホストの追加**] をクリックし、[**OK**] をクリックします。 
    
7. すべて終了したら [**完了**] をクリックします。
    

