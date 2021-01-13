---
title: Skype for Business Server の Exchange ストレージとの統合を構成する
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 8f48b87f-a57f-4ed8-8c79-5c75b316b696
description: '概要: このトピックでは、Skype for Business Server で Exchange ストレージとの統合を構成する方法について説明します。'
ms.openlocfilehash: 05a0c65aaca54e469f30dd5e732565f6ec0bbb4b
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49825067"
---
# <a name="configure-integration-with-exchange-storage-for-skype-for-business-server"></a>Skype for Business Server の Exchange ストレージとの統合を構成する
 
**概要:** このトピックでは、Skype for Business Server で Exchange ストレージとの統合を構成する方法について説明します。
  
展開内のすべてのユーザーに Microsoft Exchange 統合を使用する場合は、ユーザーの Skype for Business Server アーカイブ ポリシーを構成する必要があります。 代わりに、Exchange In-Place 保持ポリシーを構成して、Exchange にホームのユーザーのメールボックスを保持In-Placeします。 Exchange ストレージとの統合を構成する前に、「Skype for Business Server でのアーカイブの [計画」を参照してください](../../plan-your-deployment/archiving/archiving.md)。 Exchange In-Place保持ポリシーの詳細については、Exchange 製品ドキュメントを参照してください。 
  
## <a name="configure-integration-with-microsoft-exchange-storage"></a>Microsoft Exchange ストレージとの統合を構成する

1. CsArchivingAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。
    
2. ブラウザー ウィンドウを開き、管理 URL を入力して Skype for Business Server コントロール パネルを開きます。 
    
3. 左側のナビゲーション バーで、[**監視とアーカイブ**] をクリックし、[**アーカイブ構成**] をクリックします。
    
4. アーカイブ構成一覧で、適切なグローバル構成、サイト構成、またはプール構成の名前をクリックし、[**編集**]、[**詳細の表示**] の順にクリックして、次の操作を実行します。
    
   - Exchange ストレージとの統合を有効にするには **、[Microsoft Exchange 統合] チェック ボックスを** オンにします。
    
   - Exchange ストレージとの統合を無効にするには、[Microsoft Exchange 統合] **チェック ボックスを** オフにします。
    
5. [**確定**] をクリックします。
    
## <a name="when-skype-for-business-server-and-microsoft-exchange-are-deployed-in-different-forests"></a>Skype for Business Server と Microsoft Exchange が異なるフォレストに展開されている場合

Microsoft Exchange 統合を使用し、Microsoft Exchange Server が Skype for Business Server と同じフォレストに展開されていない場合は、次の Exchange Active Directory 属性が Skype for Business Server が展開されているフォレストと同期する必要があります。
  
- msExchUserHoldPolicies
    
- proxyAddresses
    
これは複数値の属性です。この属性を同期するときは、値を置き換えるのではなく値をマージして、既存の値が失われないようにする必要があります。
  

