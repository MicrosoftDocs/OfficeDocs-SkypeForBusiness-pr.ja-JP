---
title: Exchange の記憶域を持つ Skype のビジネス サーバーの統合を構成します。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 8f48b87f-a57f-4ed8-8c79-5c75b316b696
description: '概要: は、Skype での Exchange の記憶域を持つビジネス サーバーの統合を構成する方法については、このトピックを読みます。'
ms.openlocfilehash: 4b9d689ef5315c58b2fb6d78c01366ce2377a00e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "33893547"
---
# <a name="configure-integration-with-exchange-storage-for-skype-for-business-server"></a>Exchange の記憶域を持つ Skype のビジネス サーバーの統合を構成します。
 
**の概要:** Skype で Exchange の記憶域を持つビジネス サーバーの統合を構成する方法については、このトピックを参照してください。
  
配置内のすべてのユーザーの Microsoft Exchange の統合を使用する場合、ユーザーのアーカイブ ・ ポリシーをビジネス サーバー用 Skype を構成する必要はありません。 代わりに、インプレース保持に自分のメールボックスに、exchange の置かれているユーザー用にアーカイブをサポートするための Exchange インプレース保持ポリシーを構成します。 Exchange ストレージ統合を構成する前に、 [Skype のビジネス サーバーでアーカイブするための計画](../../plan-your-deployment/archiving/archiving.md)を読み取る。 Exchange インプレース保持ポリシーの詳細については、Exchange 製品のマニュアルを参照してください。 
  
## <a name="configure-integration-with-microsoft-exchange-storage"></a>Microsoft Exchange ストレージ統合を構成します。

1. CsArchivingAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。
    
2. 、ブラウザー ウィンドウを開き、を開くには、Skype ビジネス サーバーのコントロール パネルの管理 URL を入力します。 
    
3. 左側のナビゲーション バーで、[**監視とアーカイブ**] をクリックし、[**アーカイブ構成**] をクリックします。
    
4. アーカイブ構成の一覧から、適切なグローバル構成、サイト構成、またはプール構成の名前をクリックし、[**編集**]、[**詳細の表示**] の順にクリックし、次の操作を実行します。
    
   - Exchange ストレージとの統合を有効にするには、 **Microsoft Exchange の統合**] チェック ボックスを選択します。
    
   - Exchange ストレージとの統合を無効にするには、 **Microsoft Exchange の統合**] チェック ボックスをオフにします。
    
5. [**コミット**] をクリックします。
    
## <a name="when-skype-for-business-server-and-microsoft-exchange-are-deployed-in-different-forests"></a>Business Server と Microsoft Exchange の Skype が別々 のフォレストに配置されるとき

Microsoft Exchange の統合を使用するビジネス サーバーの Skype と同じフォレストに Microsoft Exchange Server が展開されない場合は、次の Exchange の Active Directory 属性がフォレストに同期されていることを確認してください、Skype のビジネス サーバーを展開します。
  
- msExchUserHoldPolicies
    
- proxyAddresses
    
これは複数値の属性です。この属性を同期するときは、値を置き換えるのではなく値をマージして、既存の値が失われないようにする必要があります。
  

