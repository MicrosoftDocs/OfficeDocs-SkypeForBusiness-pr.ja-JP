---
title: サーバー用のストレージExchange統合を構成Skype for Business Server
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 8f48b87f-a57f-4ed8-8c79-5c75b316b696
description: '概要: このトピックを参照して、ストレージ内のストレージとの統合Exchange構成する方法Skype for Business Server。'
ms.openlocfilehash: f1b6c028622edfe726b32f5fc4788668aaf4e51e
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/05/2022
ms.locfileid: "62393439"
---
# <a name="configure-integration-with-exchange-storage-for-skype-for-business-server"></a>サーバー用のストレージExchange統合を構成Skype for Business Server
 
**概要:** このトピックでは、ストレージ内のストレージとの統合Exchange構成する方法Skype for Business Server。
  
展開内のすべてのユーザー Exchange Microsoft Exchange統合を使用する場合は、ユーザーのアーカイブ ポリシー Skype for Business Server構成する必要があります。 代わりに、Exchange In-Place 保持ポリシーを構成して、Exchange に設定されているユーザーのアーカイブをサポートし、メールボックスを In-Place 保持します。 ストレージとの統合を構成する前Exchange、「アーカイブ[の計画」](../../plan-your-deployment/archiving/archiving.md)を参照Skype for Business Server。 保留ポリシーのExchange In-Placeについては、製品のドキュメントExchange参照してください。 
  
## <a name="configure-integration-with-microsoft-exchange-storage"></a>Microsoft Exchangeストレージとの統合を構成する

1. CsArchivingAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。
    
2. ブラウザー ウィンドウを開き、管理者 URL を入力して[コントロール パネル] Skype for Business Server開きます。 
    
3. 左側のナビゲーション バーで、[**監視とアーカイブ**] をクリックし、[**アーカイブ構成**] をクリックします。
    
4. アーカイブ構成一覧で、適切なグローバル構成、サイト構成、またはプール構成の名前をクリックし、[**編集**]、[**詳細の表示**] の順にクリックして、次の操作を実行します。
    
   - ストレージとの統合を有効Exchange、Microsoft の統合Exchange **チェック ボックスを** オンにします。
    
   - ストレージとの統合をExchangeするには、[Microsoft の統合Exchange **チェック ボックスを** オフにします。
    
5. [**確定**] をクリックします。
    
## <a name="when-skype-for-business-server-and-microsoft-exchange-are-deployed-in-different-forests"></a>ユーザー Skype for Business Server Microsoft Exchangeフォレストに展開する場合

Microsoft Exchange 統合を使用し、Microsoft Exchange Server が Skype for Business Server と同じフォレストに展開されていない場合は、次の Exchange Active Directory 属性がフォレストに同期されている必要があります。Skype for Business Server展開されます。
  
- msExchUserHoldPolicies
    
- proxyAddresses
    
これは複数値の属性です。この属性を同期するときは、値を置き換えるのではなく値をマージして、既存の値が失われないようにする必要があります。
  

