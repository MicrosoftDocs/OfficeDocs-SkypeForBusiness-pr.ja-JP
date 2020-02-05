---
title: Skype for Business Server の Exchange ストレージとの統合を構成する
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 8f48b87f-a57f-4ed8-8c79-5c75b316b696
description: '概要: Skype for Business Server で Exchange ストレージとの統合を構成する方法については、このトピックをお読みください。'
ms.openlocfilehash: cee41a52593a90490ec8da90637ee4ec5de33d03
ms.sourcegitcommit: dd3a3ab4ddbdcfe772f30fb01ba3b97c45c43dd4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41768890"
---
# <a name="configure-integration-with-exchange-storage-for-skype-for-business-server"></a>Skype for Business Server の Exchange ストレージとの統合を構成する
 
**概要:** このトピックでは、Skype for Business Server で Exchange ストレージとの統合を構成する方法について説明します。
  
展開のすべてのユーザーに対して Microsoft Exchange 統合を使用している場合は、ユーザーに対して Skype for Business Server アーカイブポリシーを構成する必要はありません。 代わりに、exchange を使用しているユーザーのアーカイブをサポートするように Exchange のインプレースホールドポリシーを構成します。メールボックスは、インプレースホールドに配置されています。 Exchange 記憶域との統合を構成する前に、「 [Skype For Business Server のアーカイブの計画](../../plan-your-deployment/archiving/archiving.md)」を参照してください。 Exchange のインプレースホールドポリシーの詳細については、Exchange の製品に関するドキュメントを参照してください。 
  
## <a name="configure-integration-with-microsoft-exchange-storage"></a>Microsoft Exchange storage との統合を構成する

1. CsArchivingAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。
    
2. ブラウザーウィンドウを開き、管理 URL を入力して、Skype for Business Server コントロールパネルを開きます。 
    
3. 左側のナビゲーション バーで、[**監視とアーカイブ**] をクリックし、[**アーカイブ構成**] をクリックします。
    
4. アーカイブ構成の一覧から、適切なグローバル構成、サイト構成、またはプール構成の名前をクリックし、[**編集**]、[**詳細の表示**] の順にクリックし、次の操作を実行します。
    
   - Exchange 記憶域との統合を有効にするには、[ **Microsoft Exchange 統合**] チェックボックスをオンにします。
    
   - Exchange ストレージとの統合を無効にするには、[ **Microsoft Exchange 統合**] チェックボックスをオフにします。
    
5. [**コミット**] をクリックします。
    
## <a name="when-skype-for-business-server-and-microsoft-exchange-are-deployed-in-different-forests"></a>Skype for Business Server と Microsoft Exchange がさまざまなフォレストに展開されている場合

Microsoft exchange 統合を使用していて、Microsoft Exchange Server が Skype for Business Server と同じフォレストに展開されていない場合は、次の Exchange Active Directory 属性が Skype for business Server と同じフォレストに同期されていることを確認する必要があります。Business Server が展開されます。
  
- msExchUserHoldPolicies
    
- proxyAddresses
    
これは複数値の属性です。この属性を同期するときは、値を置き換えるのではなく値をマージして、既存の値が失われないようにする必要があります。
  

