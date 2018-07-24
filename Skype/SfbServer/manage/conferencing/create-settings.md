---
title: 作成会議の Skype ビジネス サーバーの構成設定
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 6d8f9ff8-2a04-4175-9bf0-1ec5d78fd015
description: '概要: 作成する方法を説明する Skype ビジネス サーバーの構成設定に対応します。'
ms.openlocfilehash: 8826bee3a5f96fd3d30bdc999db97f796f8a0b8e
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/24/2018
ms.locfileid: "20997418"
---
# <a name="create-meeting-configuration-settings-in-skype-for-business-server"></a>作成会議の Skype ビジネス サーバーの構成設定
 
**の概要:** 作成する方法を学習 Skype ビジネス サーバーの構成設定に対応します。
  
作成することができます Skype ビジネス サーバーのコントロール パネルを使用するか、Skype ビジネス サーバー管理シェルを使用して会議の構成設定。
  
## <a name="create-meeting-configuration-settings-by-using-skype-for-business-server-control-panel"></a>作成ビジネス サーバーのコントロール パネルの Skype を使用して、会議の構成設定

1. CsUserAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。
    
2.  Skype をビジネス サーバーのコントロール パネルを開きます。
    
3. 左側のナビゲーション バーで、[**会議**] をクリックし、[**会議の構成**] をクリックします。
    
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
    
9. 参加者に送られる会議の招待をカスタマイズするには、以下を行います。 URL およびカスタム フッター テキストの長さは最大 1 KB です。 [**ヘルプ URL**] 以外は、カスタムの値を指定しない場合、会議に含まれません。 カスタム ヘルプの URL を指定しないと、ビジネスの Skype の既定のヘルプの URL 部分は招待状になります。 
    
   - 会議の招待に表示されるロゴをカスタマイズするには、[**ロゴ URL**] にロゴの場所を入力します。ロゴは、サイズが 188 x 30 ピクセルの GIF または JPG 画像である必要があります。 
    
   - 会議招待に表示されるヘルプ テキストをカスタマイズするには、[**ヘルプ URL**] にヘルプ テキストの場所を入力します。
    
   - 会議の招待に表示される法的情報をカスタマイズするには、[**リーガル テキスト URL**] にリーガル テキストの場所を入力します。
    
   - 会議の招待に表示されるカスタム フッター テキストをカスタマイズするには、[**カスタム フッターのテキスト**] にテキストを入力します。
    
10. [**確定**] をクリックします。
    
## <a name="create-meeting-configuration-settings-by-using-skype-for-business-server-management-shell"></a>作成ビジネス サーバー管理シェルの Skype を使用して、会議の構成設定

会議の構成設定を作成するには、**New-CsMeetingConfiguration** コマンドレットを使用します。
  
次のコマンドは、Redmond サイト用に会議構成設定の新しいセットを作成しています。
  
```
New-CsMeetingConfiguration -Identity "site:Redmond"
```

上記のコマンドでは必須の Identity パラメーター以外のパラメーターは指定されていないため、新しい会議構成設定はすべてのプロパティについて既定値を使用します。
  
異なるプロパティ値を使用する設定を作成するには、適切なパラメーターとパラメーター値を指定します。たとえば、会議の全員が発表者となることを既定で許可する会議構成設定のセットを作成するには、次のようなコマンドを使用します。
  
```
New-CsMeetingConfiguration -Identity "site:Redmond" -DesignateAsPresenter "Everyone"
```

複数のパラメーターを含めることにより複数のプロパティ値を設定できます。たとえば、次のコマンドは、会議の全員が発表者となることを許可し、さらに PSTN ユーザーは会議に対して正式に承認されるまで必ずロビーで待機するように設定しています。
  
```
New-CsMeetingConfiguration -Identity "site:Redmond" -DesignateAsPresenter "Everyone" -PSTNUCallersBypassLobby $True
```

パラメーターの完全な一覧を含む詳細については、[新規 CsMeetingConfiguration](https://docs.microsoft.com/powershell/module/skype/new-csmeetingconfiguration?view=skype-ps)を参照してください。
  

