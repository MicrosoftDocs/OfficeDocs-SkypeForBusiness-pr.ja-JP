---
title: ビジネス サーバーの Skype でのアーカイブ ・ ポリシーを管理します。
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 75ce32ba-eb82-4339-9c02-5df5f2c2ebd2
description: '概要: は、Skype のビジネス サーバーのアーカイブのユーザー ポリシーを管理する方法を説明します。'
ms.openlocfilehash: 289902ded6f1530c74f9c945517a3c853c99d364
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "32211056"
---
# <a name="manage-archiving-policies-in-skype-for-business-server"></a>ビジネス サーバーの Skype でのアーカイブ ・ ポリシーを管理します。

**の概要:** Skype ビジネス サーバーのアーカイブのユーザー ポリシーを管理する方法について説明します。
  
最初に、アーカイブを展開するが、変更、追加、および展開後の構成を削除すると、アーカイブ ポリシーを設定します。 アーカイブ ・ ポリシーは、アーカイブするかどうかを決定します。 
  
- 内部通信
    
- 外部通信
    
グローバル設定、サイト、またはユーザー レベル、アーカイブ ポリシーにすることができます。
  
> [!NOTE]
> 場合は有効にする Microsoft Exchange の統合、展開、Exchange ポリシーの管理に Exchange のホーム サーバーはユーザーのアーカイブが有効になっているし、インプレース保持に自分のメールボックスを配置するかどうか。 詳細については、 [Skype のビジネス サーバーでアーカイブするための計画](../../plan-your-deployment/archiving/archiving.md)と[構成との統合 Skype ビジネス サーバー用の Exchange の記憶域](../../deploy/deploy-archiving/configure-integration-with-exchange-storage.md)を参照してください。 
  
## <a name="manage-archiving-policies-by-using-the-control-panel"></a>コントロール パネルを使用してアーカイブ ポリシーを管理する

次のようにコントロール パネルを使用すると、アーカイブ ポリシーを管理することができます。
  
1. CsArchivingAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。 
    
2. 、ブラウザー ウィンドウを開き、を開くには、Skype ビジネス サーバーのコントロール パネルの管理 URL を入力します。 
    
3. 左側のナビゲーション バーで [**アーカイブ ポリシー**] をクリックします。
    
## <a name="manage-archiving-policies-by-using-windows-powershell"></a>Windows PowerShell を使用してアーカイブ ポリシーを管理する

次の表に示す Windows PowerShell コマンドレットを使用してアーカイブ ポリシーを構成することもできます。 含むすべての利用可能なパラメーターの構文の詳細については、[ビジネス サーバー管理シェルの Skype](../management-shell.md)を参照してください。
  

|**コマンドレット**|**説明**|
|:-----|:-----|
|Get-CsArchivingPolicy  <br/> |組織のインスタント メッセージング (IM) セッションのアーカイブ ポリシーに関する情報を戻します。  <br/> |
|Grant-CsArchivingPolicy  <br/> |インスタント メッセージング (IM) セッションのアーカイブ ポリシーをユーザーまたはユーザー セットに割り当てます。 これらのポリシーにより、内部ユーザー間で行われるすべての IM セッションをアーカイブしたり、内部ユーザーと外部パートナー間で行われるすべての IM セッションをアーカイブしたりすることができます。  <br/> |
|New-CsArchivingPolicy  <br/> |新しいインスタント メッセージング (IM) セッション アーカイブ ポリシーを作成します。 これらのポリシーを使用すると、内部ユーザーどうし、または内部ユーザーと外部パートナーとの間で生じるすべての IM セッションをアーカイブできます。  <br/> |
|Remove-CsArchivingPolicy  <br/> |指定したインスタント メッセージング (IM) アーカイブ ビジネス サーバーの Skype の内部ユーザー、および内部ユーザーとフェデレーション パートナーとの間のすべての IM セッションの間で行われるすべての IM セッションが自動的に保存するかどうかを決定するポリシーを削除します。  <br/> |
|Set-CsArchivingPolicy  <br/> |既存インスタント メッセージング (IM) アーカイブ ポリシーを変更します。 アーカイブ ポリシーは、すべての IM セッションおよび内部ユーザー間で行われる会議をアーカイブする機能を提供します。内部ユーザーとフェデレーション パートナーの間で行われるセッションをアーカイブすることもできます。  <br/> |
   

