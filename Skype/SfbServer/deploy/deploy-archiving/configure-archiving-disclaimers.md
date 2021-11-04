---
title: 外部ユーザーのアーカイブに関する免責事項を構成Skype for Business Server
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
ms.assetid: 394ac291-05cd-4fa1-acb3-714af538b47f
description: '概要: このトピックでは、アーカイブに関する免責事項を構成する方法について説明Skype for Business Server。'
ms.openlocfilehash: a5777a416d634f6d767efbec97f2c72bc7899c47
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/04/2021
ms.locfileid: "60773397"
---
# <a name="configure-archiving-disclaimers-for-external-users-in-skype-for-business-server"></a>外部ユーザーのアーカイブに関する免責事項を構成Skype for Business Server
 
**概要:** このトピックでは、アーカイブに関する免責事項を構成する方法について説明Skype for Business Server。
  
組織が外部パートナーと通信する場合は、そのパートナーとの通信をアーカイブしている必要があります。 エッジ サーバーを展開し、組織のフェデレーションを有効にするときに、アーカイブに関する免責事項を外部パートナーに自動的に送信するかどうかを確認するメッセージが表示されます。 
  
この構成を変更する必要がある場合は、Skype for Business Server **Set-CsAccessEdgeConfiguration** コマンドレットWindows PowerShell使用できます。 コマンドレットは、管理シェルまたはSkype for Business Serverリモート セッションから実行Windows PowerShell。
  
外部ユーザーが Skype for Business Server 展開内のユーザーと共同作業を行う場合は、外部ユーザー アクセスをサポートするために、少なくとも 1 つの外部アクセス ポリシーを構成する必要があります。 詳細については、「Manage XMPP Federated Partners for Your Organization」を参照してください。 特定のフェデレーション ドメインのアクセス制御の詳細については、「個々のフェデレーション ドメインによるアクセスの制御」を参照してください。
  
## <a name="enable-or-disable-archiving-disclaimer-using-the-control-panel"></a>コントロール パネルを使用してアーカイブの免責事項を有効または無効にする

1. RTCUniversalServerAdmins グループ (または同等のユーザー権限を持つグループ) のメンバーであるユーザー アカウントまたは CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。
    
2. ブラウザー ウィンドウを開き、管理者 URL を入力して[コントロール パネル] Skype for Business Server開きます。 
    
3. 左側のナビゲーション バーで [**フェデレーションと外部アクセス**] をクリックし、[**アクセス エッジ構成**] をクリックします。
    
4. [**アクセス エッジ構成**] タブで、[**グローバル**] をクリックし、[**編集**] をクリックしてから、[**詳細の表示**] をクリックします。
    
5. [**アクセス** エッジ構成の編集] の [フェデレーションとパブリック **IM** 接続を有効にする] で、[アーカイブ免責事項をフェデレーション パートナーに送信する] チェック ボックスをオンまたはオフにして、アーカイブ免責事項の自動送信を有効または無効にします。
    
6. [**確定**] をクリックします。
    
## <a name="enable-or-disable-archiving-disclaimer-using-windows-powershell"></a>サーバーを使用してアーカイブの免責事項を有効または無効Windows PowerShell

アーカイブについての免責事項を有効にするには、**EnableArchivingDisclaimer** プロパティの値を True ($True) に設定します。
  
```powershell
Set-CsAccessEdgeConfiguration -EnableArchivingDisclaimer $True
```

アーカイブについての免責事項を有効にするには、**EnableArchivingDisclaimer** プロパティの値を False ($False) に設定します。
  
```powershell
Set-CsAccessEdgeConfiguration -EnableArchivingDisclaimer $False
```


