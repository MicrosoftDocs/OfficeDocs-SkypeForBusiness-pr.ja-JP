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
ms.localizationpriority: medium
description: この手順を正常に完了するには、Domain Admins グループまたは DnsAdmins グループのメンバーとしてサーバーまたはドメインにログオンしている必要があります。
ms.openlocfilehash: 1b88ada924cbf2cf7f4153acda54584d81946cb0
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/26/2021
ms.locfileid: "58579421"
---
# <a name="update-dns-srv-records"></a>DNS SRV レコードの更新

この手順を正常に完了するには、Domain Admins グループまたは DnsAdmins グループのメンバーとしてサーバーまたはドメインにログオンしている必要があります。
  
このトピックでは、ドメイン ネーム システム (DNS) レコードを 2019 年に移行した後に更新Skype for Business Serverします。 すべてのユーザーが Skype for Business Server 2019 に移動された後、レガシ プールまたはディレクターが使用停止される前に、すべての SIP ドメインの内部 DNS の DNS SRV レコードを更新する必要があります。 この手順では、内部 DNS に SIP ユーザー ドメインの領域が含まれると仮定します。
  
## <a name="to-configure-a-dns-srv-record"></a>DNS SRV レコードを構成するには

1. DNS サーバー上で、[**スタート**] をクリックし、[**管理ツール**] をクリックします。次に、[**DNS**] をクリックします。
    
2. SIP ドメインのコンソール ツリーで、[前方参照ゾーン] を展開し、Skype for Business Server 2019 がインストールされている SIP ドメインを展開し、_tcp 設定 **に移動** します。 
    
3. 右側のウィンドウで、[プロパティ] を右クリック **して_sipinternaltls** を **選択します**。
    
4. [**このサービスを提供するホスト]** で、ホスト FQDN を更新して、2019 年Skype for Business Serverをポイントします。
    
5. **[OK]** をクリックします。
    
## <a name="to-verify-that-the-fqdn-of-the-front-end-pool-or-standard-edition-server-can-be-resolved"></a>フロントエンド プールまたは Standard Edition サーバーの FQDN が解決できることを確認するには

1. ドメイン内のクライアント コンピューターにログオンします。
    
2. [**スタート**] ボタンをクリックし、[**ファイル名を指定して実行**] をクリックします。
    
3. [開く **] ボックス** に「cmd」と入力し **、[OK] をクリックします**。
    
4. コマンド プロンプトで、nslookup _\<FQDN of the Front End pool\>_ または を入力し  _\<FQDN of the Standard Edition server\>_ 、Enter キーを押します。
    
5. 受け取る応答が、FQDN の適切な IP アドレスに解決しているのを確認します。
    

