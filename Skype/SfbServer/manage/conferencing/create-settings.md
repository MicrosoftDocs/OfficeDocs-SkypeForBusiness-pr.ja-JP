---
title: 会議の構成設定を作成Skype for Business Server
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 6d8f9ff8-2a04-4175-9bf0-1ec5d78fd015
description: '概要: 会議の構成設定を作成する方法について説明します。Skype for Business Server。'
ms.openlocfilehash: 03a9194a5b4015d9434641e7946b66c57ff4df77
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/04/2021
ms.locfileid: "60747153"
---
# <a name="create-meeting-configuration-settings-in-skype-for-business-server"></a>会議の構成設定を作成Skype for Business Server
 
**概要:** 会議の構成設定を作成する方法については、Skype for Business Server。
  
会議構成設定は、コントロール パネルまたは管理シェルSkype for Business Server使用してSkype for Business Server作成できます。
  
## <a name="create-meeting-configuration-settings-by-using-skype-for-business-server-control-panel"></a>[コントロール パネル] を使用して会議Skype for Business Server設定を作成する

1. CsUserAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。
    
2.  [コントロール Skype for Business Server] を開きます。
    
3. 左側のナビゲーション バーで、[会議] **をクリックし**、[会議の構成] **をクリックします**。
    
4. [**会議の構成**] ページで、[**新規作成**] をクリックし、次のいずれかを実行します。
    
    - サイト レベルのポリシーを作成するには、[**サイト構成**] をクリックします。[**サイトの選択**] 検索フィールドに、会議参加設定を定義するサイトの名前の全体または一部を入力します。サイトの結果一覧で対象のサイトをクリックして、[**OK**] をクリックします。
    
    - プール レベルのポリシーを作成するには、[**プール構成**] をクリックします。[**サービスの選択**] 検索フィールドに、会議参加設定を定義するプール サービスの名前の全体または一部を入力します。サービスの結果一覧で、対象のプールをクリックして [**OK**] をクリックします。
    
5. 公衆交換電話網 (PSTN) からダイヤルインする参加者をロビーを介してルーティングするには、[**PSTN 発信者はロビーをバイパスする**] チェック ボックスをオフにします。既定では、PSTN からダイヤルインした参加者は会議に直接移動します。
    
6. 会議の発表者になることができるユーザーを構成するには、[**発表者として指定**] で、次のいずれかの操作を実行します。
    
   - 開催者以外のユーザーが発表者になることを許可しない場合は、[**なし**] をクリックします。
    
   - 組織のメンバーになっている参加者にのみ発表者になることを許可する場合は、[**会社**] をクリックします。これは既定の設定です。
    
   - 参加者すべてに発表者になることを許可する場合は、[**全員**] をクリックします。
    
7. 開催者が会議のスケジュール時に会議の種類を選択できるようにするには、[**既定で割り当てられた会議の種類**] チェック ボックスをオフにします。既定では、会議の種類が自動的に割り当てられます。
    
8. 匿名 (未認証) ユーザーが自動的に承認されないようにするには、[**既定で匿名ユーザーを承認する**] チェック ボックスをオフにします。既定では、匿名ユーザーは会議に対して自動的に承認されます。
    
9. 参加者に送られる会議の招待をカスタマイズするには、以下を行います。 URL およびカスタム フッター テキストの長さは最大 1 KB です。 [**ヘルプ URL**] 以外は、カスタムの値を指定しない場合、会議に含まれません。 カスタム ヘルプ URL を含めない場合は、招待にSkype for Business既定のヘルプ URL が表示されます。 
    
   - 会議の招待に表示されるロゴをカスタマイズするには、[**ロゴ URL**] にロゴの場所を入力します。 ロゴは、サイズが 188 x 30 ピクセルの GIF または JPG 画像である必要があります。 
    
   - 会議招待に表示されるヘルプ テキストをカスタマイズするには、[**ヘルプ URL**] にヘルプ テキストの場所を入力します。
    
   - 会議の招待に表示される法的情報をカスタマイズするには、[**リーガル テキスト URL**] にロゴの場所を入力します。
    
   - 会議の招待に表示されるカスタム フッター テキストをカスタマイズするには、[**カスタム フッターのテキスト**] にテキストを入力します。
    
10. [**確定**] をクリックします。
    
## <a name="create-meeting-configuration-settings-by-using-skype-for-business-server-management-shell"></a>管理シェルを使用して会議の構成Skype for Business Server作成する

会議構成設定を作成するには **、New-CsMeetingConfiguration コマンドレットを使用** します。
  
次のコマンドは、Redmond サイトの会議構成設定の新しいセットを作成します。
  
```PowerShell
New-CsMeetingConfiguration -Identity "site:Redmond"
```

上記のコマンドでは必須の Identity パラメーター以外のパラメーターは指定されていないため、新しい会議構成設定はすべてのプロパティについて既定値を使用します。
  
異なるプロパティ値を使用する設定を作成するには、適切なパラメーターとパラメーター値を指定します。たとえば、会議の全員が発表者となることを既定で許可する会議構成設定のセットを作成するには、次のようなコマンドを使用します。
  
```PowerShell
New-CsMeetingConfiguration -Identity "site:Redmond" -DesignateAsPresenter "Everyone"
```

複数のパラメーターを含めて、複数のプロパティ値を設定できます。 たとえば、次のコマンドは、全員が発表者として会議に参加し、PSTN ユーザーが会議に正式に出席するまでロビーで待機する必要があります。
  
```PowerShell
New-CsMeetingConfiguration -Identity "site:Redmond" -DesignateAsPresenter "Everyone" -PSTNUCallersBypassLobby $True
```

パラメーターの完全なリストを含む詳細については [、「New-CsMeetingConfiguration」を参照してください](/powershell/module/skype/new-csmeetingconfiguration?view=skype-ps)。
