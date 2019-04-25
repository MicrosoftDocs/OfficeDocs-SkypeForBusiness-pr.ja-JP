---
title: DNS SRV レコードの更新
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: この手順を正常に完了するには、サーバーまたはドメイン管理者グループのメンバーまたは DnsAdmins グループのメンバーとしてドメインにログオンする必要があります。
ms.openlocfilehash: 5cdf98d065abbb57b3cb654c8b770f8f1f87500c
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "32231384"
---
# <a name="update-dns-srv-records"></a>DNS SRV レコードの更新

この手順を正常に完了するには、サーバーまたはドメイン管理者グループのメンバーまたは DnsAdmins グループのメンバーとしてドメインにログオンする必要があります。
  
このトピックでは、ビジネス サーバー 2019 の Skype に移行した後、ドメイン ネーム システム (DNS) レコードを更新する方法について説明します。 すべてのユーザーが Skype をビジネス サーバー 2019 に移動した後ですが、従来のプールまたはディレクターの使用を中止する前に、内部 SIP ドメインごとに DNS に DNS SRV レコードを更新する必要があります。 この手順では、内部 DNS が、SIP ユーザー ドメインのゾーンを持っていると仮定します。
  
## <a name="to-configure-a-dns-srv-record"></a>DNS SRV レコードを構成するのには

1. DNS サーバーで [**スタート**] ボタンを選択し、 **[管理ツール**] をクリックし、[ **DNS**] をクリックします。
    
2. SIP ドメインのコンソール ツリーで **[前方参照ゾーン**を展開し、ビジネス サーバー 2019 をインストールし、 **「_tcp」** 設定に移動する Skype の SIP ドメインを展開します。 
    
3. 右側のウィンドウでは、 **_sipinternaltls**を右クリックし、**プロパティ**を選択します。
    
4. **このサービスを提供しているホスト**を、ホストの FQDN がプールのビジネス サーバー 2019 Skype を指すように更新します。
    
5. **[OK]** をクリックします。
    
## <a name="to-verify-that-the-fqdn-of-the-front-end-pool-or-standard-edition-server-can-be-resolved"></a>フロント エンド プールまたは Standard Edition サーバーの FQDN を解決できることを確認するには

1. ドメイン内のクライアント コンピューターにログオンします。
    
2. [**スタート**] ボタンをクリックし、[**ファイル名を指定して実行**] をクリックします。
    
3. **[名前**] ボックスに cmd と入力し、[ **OK**] をクリックします。
    
4. コマンド プロンプトで nslookup と入力します。_\<フロント エンド プールの FQDN\>_ または_\<Standard Edition サーバーの FQDN\>_、し、ENTER キーを押します。
    
5. FQDN の適切な IP アドレスに解決することを示すメッセージが表示されることを確認します。
    

