---
title: DNS SRV レコードの更新
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
description: この手順を正常に完了するには、Domain Admins グループまたは DnsAdmins グループのメンバーとしてサーバーまたはドメインにログオンしている必要があります。
ms.openlocfilehash: 26bb80618868a2bec03d1de32f6c010869b8cf8c
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/16/2020
ms.locfileid: "44753269"
---
# <a name="update-dns-srv-records"></a>DNS SRV レコードの更新

この手順を正常に完了するには、Domain Admins グループまたは DnsAdmins グループのメンバーとしてサーバーまたはドメインにログオンしている必要があります。
  
このトピックでは、Skype for Business Server 2019 に移行した後にドメインネームシステム (DNS) レコードを更新する方法について説明します。 すべてのユーザーが Skype for Business Server 2019 に移動された後、従来のプールまたはディレクターが使用停止になる前に、すべての SIP ドメインについて内部 DNS の DNS SRV レコードを更新する必要があります。 この手順では、内部 DNS に SIP ユーザードメインのゾーンがあることを前提としています。
  
## <a name="to-configure-a-dns-srv-record"></a>DNS SRV レコードを構成するには

1. DNS サーバー上で、[**スタート**] をクリックし、[**管理ツール**] をクリックします。次に、[**DNS**] をクリックします。
    
2. SIP ドメインのコンソールツリーで、[**前方参照ゾーン**] を展開し、Skype For business Server 2019 がインストールされている SIP ドメインを展開し、 **_tcp**の設定に移動します。 
    
3. 右側のウィンドウで、[ **_sipinternaltls** ] を右クリックし、[**プロパティ**] を選択します。
    
4. [**このサービスを提供**しているホスト] で、Skype For business Server 2019 プールを指すようにホストの FQDN を更新します。
    
5. **[OK]** をクリックします。
    
## <a name="to-verify-that-the-fqdn-of-the-front-end-pool-or-standard-edition-server-can-be-resolved"></a>フロントエンド プールまたは Standard Edition サーバーの FQDN が解決できることを確認するには

1. ドメイン内のクライアント コンピューターにログオンします。
    
2. [**スタート**] ボタンをクリックし、[**ファイル名を指定して実行**] をクリックします。
    
3. [**名前**] ボックスに「cmd」と入力し、[ **OK**] をクリックします。
    
4. コマンドプロンプトで「nslookup _\<FQDN of the Front End pool\>_ または _\<FQDN of the Standard Edition server\>_ 」と入力し、enter キーを押します。
    
5. 受け取る応答が、FQDN の適切な IP アドレスに解決しているのを確認します。
    

