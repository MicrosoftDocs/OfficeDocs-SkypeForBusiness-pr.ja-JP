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
localization_priority: Normal
description: パイロットプールを展開する前に、DNS ホストをパイロットプールのエントリに更新する必要があります。 この手順を正常に完了するには、Domain Admins グループまたは DnsAdmins グループのメンバーとしてサーバーまたはドメインにログオンしている必要があります。
ms.openlocfilehash: d934e3bdc46ab9deffa3c588b15ab793111c1a68
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/16/2020
ms.locfileid: "44754057"
---
# <a name="configure-dns-records-for-pilot-pool-deployment"></a>パイロット プール展開の DNS レコードの構成

パイロットプールを展開する前に、DNS ホストをパイロットプールのエントリに更新する必要があります。 この手順を正常に完了するには、Domain Admins グループまたは DnsAdmins グループのメンバーとしてサーバーまたはドメインにログオンしている必要があります。
  
### <a name="to-configure-dns-host-a-records"></a>DNS ホスト A レコードを構成するには

1. ドメイン ネーム システム (DNS) サーバーで、[**スタート**]、[**管理ツール**]、および [**DNS**] の順にクリックします。
    
2. ドメインのコンソールツリーで、[**前方参照ゾーン**] を展開し、Skype For business Server 2019 がインストールされるドメインを右クリックします。
    
3. [**新しいホスト (A または AAAA)**] をクリックします。
    
4. [**名前**] をクリックして、Skype For business Server 2019 プールのホスト名を入力します (ドメイン名は、レコードが定義されている領域から、A レコードの一部として入力する必要はありません)。
    
5. [ **Ip アドレス**] をクリックし、フロントエンドプールの ip アドレスを入力します。
    
6. [**ホストの追加**] をクリックし、[**OK**] をクリックします。 
    
7. すべて終了したら [**完了**] をクリックします。
    

