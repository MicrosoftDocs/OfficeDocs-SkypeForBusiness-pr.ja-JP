---
title: パイロット プール展開の DNS レコードの構成
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: パイロット プールを展開するには、前にパイロットのプールの DNS ホスト A のエントリを更新する必要があります。 この手順を正常に完了するには、サーバーまたはドメイン管理者グループのメンバーまたは DnsAdmins グループのメンバーとしてドメインにログオンする必要があります。
ms.openlocfilehash: 23ac5e4f85dc0da560b4d288bbfad426298bf82e
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "32238731"
---
# <a name="configure-dns-records-for-pilot-pool-deployment"></a>パイロット プール展開の DNS レコードの構成

パイロット プールを展開するには、前にパイロットのプールの DNS ホスト A のエントリを更新する必要があります。 この手順を正常に完了するには、サーバーまたはドメイン管理者グループのメンバーまたは DnsAdmins グループのメンバーとしてドメインにログオンする必要があります。
  
### <a name="to-configure-dns-host-a-records"></a>DNS ホスト A レコードを構成するのには

1. ドメイン ネーム システム (DNS) サーバー上 [**スタート**] ボタンを選択し、 **[管理ツール**] をクリックし、[ **DNS**] をクリックします。
    
2. ドメインのコンソール ツリーで **[前方参照ゾーン**] を展開し、ビジネス サーバー 2019 の Skype をインストールするドメインを右クリックし、します。
    
3. [**新しいホスト (A または AAAA)**] をクリックします。
    
4. **名**をクリックして、(ドメイン名は、ゾーンをレコードで定義されている A レコードの一部として入力する必要はありませんからと仮定します) ビジネス サーバー 2019 プールの Skype のホスト名を入力します。
    
5. **IP アドレス**] をクリックし、フロント エンド プールの IP アドレスを入力します。
    
6. **ホストの追加**をクリックし、[ **OK**] をクリックします。 
    
7. 終了したら、[**完了**] をクリックします。
    

