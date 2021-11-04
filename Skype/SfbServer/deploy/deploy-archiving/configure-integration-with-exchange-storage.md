---
title: サーバー用のストレージExchange統合を構成Skype for Business Server
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 8f48b87f-a57f-4ed8-8c79-5c75b316b696
description: '概要: このトピックを参照して、ストレージ内のストレージとの統合Exchange構成する方法Skype for Business Server。'
ms.openlocfilehash: 3ac2db718057b47ebe214c29e339b94dbc5e63a7
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/04/2021
ms.locfileid: "60759189"
---
# <a name="configure-integration-with-exchange-storage-for-skype-for-business-server"></a>サーバー用のストレージExchange統合を構成Skype for Business Server
 
**概要:** このトピックでは、ストレージ内のストレージとの統合Exchange構成する方法Skype for Business Server。
  
展開内のすべてのユーザー Exchange Microsoft Exchange統合を使用する場合は、ユーザーのアーカイブ ポリシー Skype for Business Server構成する必要があります。 代わりに、Exchange In-Place 保持ポリシーを構成して、Exchange に設定されているユーザーのアーカイブをサポートし、メールボックスを In-Place 保持します。 ストレージとの統合を構成する前Exchange、「アーカイブの計画[」を参照Skype for Business Server。](../../plan-your-deployment/archiving/archiving.md) 保留ポリシーのExchange In-Placeについては、製品のドキュメントExchange参照してください。 
  
## <a name="configure-integration-with-microsoft-exchange-storage"></a>Microsoft Exchangeストレージとの統合を構成する

1. CsArchivingAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。
    
2. ブラウザー ウィンドウを開き、管理者 URL を入力して[コントロール パネル] Skype for Business Server開きます。 
    
3. 左側のナビゲーション バーで、[**監視とアーカイブ**] をクリックし、[**アーカイブ構成**] をクリックします。
    
4. アーカイブ構成一覧で、適切なグローバル構成、サイト構成、またはプール構成の名前をクリックし、[**編集**]、[**詳細の表示**] の順にクリックして、次の操作を実行します。
    
   - ストレージとの統合を有効Exchange、Microsoft の [統合] チェック **Exchange選択** します。
    
   - ストレージとの統合を無効Exchange、Microsoft の [統合] チェック **Exchangeオフ** にします。
    
5. [**確定**] をクリックします。
    
## <a name="when-skype-for-business-server-and-microsoft-exchange-are-deployed-in-different-forests"></a>ユーザー Skype for Business Server Microsoft Exchangeフォレストに展開する場合

Microsoft Exchange 統合を使用し、Microsoft Exchange Server が Skype for Business Server と同じフォレストに展開されていない場合は、次の Exchange Active Directory 属性が、Skype for Business Server が展開されているフォレストに同期されている必要があります。
  
- msExchUserHoldPolicies
    
- proxyAddresses
    
これは複数値の属性です。この属性を同期するときは、値を置き換えるのではなく値をマージして、既存の値が失われないようにする必要があります。
  

