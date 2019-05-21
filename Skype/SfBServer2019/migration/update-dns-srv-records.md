---
title: DNS SRV レコードの更新
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: この手順を完了するには、サーバーまたはドメインに、Domain Admins グループのメンバーまたは DnsAdmins グループのメンバーとしてログオンしている必要があります。
ms.openlocfilehash: bf9f9c3f16ceb2ee35cda8e833d468e202d5653c
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34307057"
---
# <a name="update-dns-srv-records"></a>DNS SRV レコードの更新

この手順を完了するには、サーバーまたはドメインに、Domain Admins グループのメンバーまたは DnsAdmins グループのメンバーとしてログオンしている必要があります。
  
このトピックでは、Skype for Business Server 2019 に移行した後に、ドメインネームシステム (DNS) レコードを更新する方法について説明します。 すべてのユーザーが Skype for Business Server 2019 に移動された後、以前のプールまたはディレクターが廃止される前に、すべての SIP ドメインの内部 DNS の DNS SRV レコードを更新する必要があります。 この手順では、内部 DNS に SIP ユーザードメイン用のゾーンが含まれていることを前提としています。
  
## <a name="to-configure-a-dns-srv-record"></a>DNS SRV レコードを構成するには

1. DNS サーバーで [**スタート**] をクリックし、[**管理ツール**]、[ **dns**] の順にクリックします。
    
2. SIP ドメインのコンソールツリーで [**前方参照ゾーン**] を展開し、Skype For business Server 2019 がインストールされている SIP ドメインを展開して、 **_tcp**設定に移動します。 
    
3. 右側のウィンドウで、[ **_sipinternaltls** ] を右クリックし、[**プロパティ**] を選択します。
    
4. [**このサービスを提供**しているホスト] で、[Skype For business Server 2019 プール] をポイントするようにホストの FQDN を更新します。
    
5. **[OK]** をクリックします。
    
## <a name="to-verify-that-the-fqdn-of-the-front-end-pool-or-standard-edition-server-can-be-resolved"></a>フロントエンドプールまたは Standard Edition サーバーの FQDN が解決できることを確認するには

1. ドメイン内のクライアントコンピューターにログオンします。
    
2. [**スタート**] ボタンをクリックし、[**ファイル名を指定して実行**] をクリックします。
    
3. [**開く**] ボックスに cmd と入力し、[ **OK**] をクリックします。
    
4. コマンドプロンプトに、 _ \<標準エディションサーバー\>の_ _ \<フロントエンドプール\> _または fqdn の nslookup FQDN と入力して、enter キーを押します。
    
5. FQDN の適切な IP アドレスに解決される返信を受信したことを確認します。
    

