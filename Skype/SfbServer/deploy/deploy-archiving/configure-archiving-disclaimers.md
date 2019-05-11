---
title: Skype のビジネス サーバーの外部のユーザーのアーカイブの免責事項を構成します。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 394ac291-05cd-4fa1-acb3-714af538b47f
description: '概要: は、Skype のビジネス サーバーのアーカイブの免責事項を構成する方法の詳細については、このトピックを読みます。'
ms.openlocfilehash: 7cc1c5c770a20c9ccd4d1473eeca4147042fde95
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "33894156"
---
# <a name="configure-archiving-disclaimers-for-external-users-in-skype-for-business-server"></a>Skype のビジネス サーバーの外部のユーザーのアーカイブの免責事項を構成します。
 
**の概要:** Skype のビジネス サーバーのアーカイブの免責事項を構成する方法の詳細については、このトピックを参照してください。
  
組織で外部パートナーとの通信を行う場合は、相手との通信をアーカイブしていることを相手に伝える必要があります。 エッジ サーバーの展開、組織のフェデレーションを有効にすると、自動的にアーカイブの免責事項を外部パートナーに送信するかどうかが求められます。 
  
この構成を変更する場合は、ビジネス サーバーのコントロール パネルまたは Windows PowerShell**セット CsAccessEdgeConfiguration**コマンドレットは、Skype を使用できます。 Business Server 管理シェルの Skype とは Windows PowerShell のリモート セッションからは、コマンドレットを実行できます。
  
ビジネス サーバーの展開について、Skype ユーザーと共同作業を外部のユーザーを有効にするには、外部ユーザー アクセスをサポートするために少なくとも 1 つの外部アクセス ポリシーを構成することもあります。 詳細については、組織の XMPP フェデレーション パートナーの管理を参照してください。 特定のフェデレーション ドメインのアクセス制御の詳細については、「個別のフェデレーション ドメインごとのアクセス制御」を参照してください。
  
## <a name="enable-or-disable-archiving-disclaimer-using-the-control-panel"></a>コントロール パネルを使用してアーカイブについての免責事項を有効または無効にする

1. RTCUniversalServerAdmins グループ (または同等のユーザー権限を持つグループ) のメンバーであるユーザー アカウントまたは CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。
    
2. 、ブラウザー ウィンドウを開き、を開くには、Skype ビジネス サーバーのコントロール パネルの管理 URL を入力します。 
    
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


