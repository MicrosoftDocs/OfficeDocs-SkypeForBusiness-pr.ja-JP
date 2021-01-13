---
title: Skype for Business Server で外部ユーザーのアーカイブ免責事項を構成する
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
ms.assetid: 394ac291-05cd-4fa1-acb3-714af538b47f
description: '概要: このトピックでは、Skype for Business Server のアーカイブについての免責事項を構成する方法について説明します。'
ms.openlocfilehash: 055c94f0fba18dcd9de35ff5a73e37de0b45595b
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49820667"
---
# <a name="configure-archiving-disclaimers-for-external-users-in-skype-for-business-server"></a>Skype for Business Server で外部ユーザーのアーカイブ免責事項を構成する
 
**概要:** このトピックでは、Skype for Business Server のアーカイブについての免責事項を構成する方法について説明します。
  
組織が外部パートナーと通信する場合は、外部パートナーとの通信をアーカイブ中と知らせる必要があります。 エッジ サーバーを展開し、組織のフェデレーションを有効にするときに、アーカイブについての免責事項を外部パートナーに自動的に送信するかどうかを確認するメッセージが表示されます。 
  
この構成を変更する必要がある場合は、Skype for Business Server コントロール パネルまたは Windows PowerShell **Set-CsAccessEdgeConfiguration** コマンドレットを使用できます。 コマンドレットは、Skype for Business Server 管理シェルまたは Skype for Business Server のリモート セッションから実行Windows PowerShell。
  
外部ユーザーが Skype for Business Server 展開のユーザーと共同作業を行うのを有効にするには、外部ユーザー アクセスをサポートするために、少なくとも 1 つの外部アクセス ポリシーも構成する必要があります。 詳細については、「組織の XMPP フェデレーション パートナーの管理」を参照してください。 特定のフェデレーション ドメインのアクセス制御の詳細については、「個々のフェデレーション ドメインによるアクセスの制御」を参照してください。
  
## <a name="enable-or-disable-archiving-disclaimer-using-the-control-panel"></a>コントロール パネルを使用してアーカイブ免責事項を有効または無効にする

1. RTCUniversalServerAdmins グループ (または同等のユーザー権限を持つグループ) のメンバーであるユーザー アカウントまたは CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。
    
2. ブラウザー ウィンドウを開き、管理 URL を入力して Skype for Business Server コントロール パネルを開きます。 
    
3. 左側のナビゲーション バーで [**フェデレーションと外部アクセス**] をクリックし、[**アクセス エッジ構成**] をクリックします。
    
4. [**アクセス エッジ構成**] タブで、[**グローバル**] をクリックし、[**編集**] をクリックしてから、[**詳細の表示**] をクリックします。
    
5. [**アクセス** エッジ構成の編集] の [フェデレーションとパブリック **IM** 接続の有効化] で、[フェデレーション パートナーにアーカイブについての免責事項を送信する] チェック ボックスをオンまたはオフにして、アーカイブについての免責事項の自動送信を有効または無効にします。
    
6. [**確定**] をクリックします。
    
## <a name="enable-or-disable-archiving-disclaimer-using-windows-powershell"></a>アーカイブ免責事項を有効または無効にするには、次のWindows PowerShell

アーカイブについての免責事項を有効にするには、**EnableArchivingDisclaimer** プロパティの値を True ($True) に設定します。
  
```powershell
Set-CsAccessEdgeConfiguration -EnableArchivingDisclaimer $True
```

アーカイブについての免責事項を有効にするには、**EnableArchivingDisclaimer** プロパティの値を False ($False) に設定します。
  
```powershell
Set-CsAccessEdgeConfiguration -EnableArchivingDisclaimer $False
```


