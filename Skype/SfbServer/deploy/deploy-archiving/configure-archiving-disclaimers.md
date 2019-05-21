---
title: Skype for Business Server で外部ユーザーのアーカイブの免責事項を構成する
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 394ac291-05cd-4fa1-acb3-714af538b47f
description: '概要: Skype for Business Server のアーカイブの免責事項を構成する方法については、このトピックをお読みください。'
ms.openlocfilehash: 86430ac80d85ed166ae091119f4261cdc5e1ff9b
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34278984"
---
# <a name="configure-archiving-disclaimers-for-external-users-in-skype-for-business-server"></a>Skype for Business Server で外部ユーザーのアーカイブの免責事項を構成する
 
**概要:** このトピックでは、Skype for Business Server のアーカイブの免責事項を構成する方法について説明します。
  
組織で外部パートナーとの通信を行う場合は、相手との通信をアーカイブしていることを相手に伝える必要があります。 エッジサーバーを展開して組織のフェデレーションを有効にすると、アーカイブの免責事項を外部パートナーに自動的に送信するかどうかを確認するメッセージが表示されます。 
  
この構成を変更する必要がある場合は、Skype for Business Server コントロールパネルまたは Windows PowerShell **CsAccessEdgeConfiguration**コマンドレットを使用できます。 コマンドレットは、Skype for Business Server 管理シェルから、または Windows PowerShell のリモートセッションから実行できます。
  
外部ユーザーが Skype for Business Server 展開のユーザーと共同作業できるようにするには、外部ユーザーのアクセスをサポートするために、少なくとも1つの外部アクセスポリシーを構成する必要があります。 詳細については、「組織の XMPP フェデレーションパートナーを管理する」を参照してください。 特定のフェデレーション ドメインのアクセス制御の詳細については、「個別のフェデレーション ドメインごとのアクセス制御」を参照してください。
  
## <a name="enable-or-disable-archiving-disclaimer-using-the-control-panel"></a>コントロール パネルを使用してアーカイブについての免責事項を有効または無効にする

1. RTCUniversalServerAdmins グループ (または同等のユーザー権限を持つグループ) のメンバーであるユーザー アカウントまたは CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。
    
2. ブラウザーウィンドウを開き、管理 URL を入力して、Skype for Business Server コントロールパネルを開きます。 
    
3. 左側のナビゲーション バーで [**フェデレーションと外部アクセス**] をクリックし、[**アクセス エッジ構成**] をクリックします。
    
4. [**アクセス エッジ構成**] タブで、[**グローバル**] をクリックし、[**編集**] をクリックしてから、[**詳細の表示**] をクリックします。
    
5. [**アクセス エッジ構成の編集**] の [**フェデレーションとパブリック IM 接続を有効にする**] で、[**フェデレーション パートナーにアーカイブについての免責事項を送信する**] チェック ボックスをオンまたはオフにして、アーカイブについての免責事項の自動送信を有効または無効にします。
    
6. [**確定**] をクリックします。
    
## <a name="enable-or-disable-archiving-disclaimer-using-windows-powershell"></a>Windows PowerShell を使用してアーカイブについての免責事項を有効または無効にする

アーカイブについての免責事項を有効にするには、**EnableArchivingDisclaimer** プロパティの値を True ($True) に設定します。
  
```
Set-CsAccessEdgeConfiguration -EnableArchivingDisclaimer $True
```

アーカイブについての免責事項を無効にするには、**EnableArchivingDisclaimer** プロパティの値を False ($False) に設定します。
  
```
Set-CsAccessEdgeConfiguration -EnableArchivingDisclaimer $False
```


