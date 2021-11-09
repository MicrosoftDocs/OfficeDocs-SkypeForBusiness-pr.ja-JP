---
title: 新しい PIN ポリシーを作成Skype for Business Server
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: 8bdf0478-fe9f-4371-93ff-db39381a25db
description: '概要: 新しい PIN ポリシーを作成します。Skype for Business Server。'
ms.openlocfilehash: cf9a35c634c9b53b557601009fa131c3c24e7db2
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/08/2021
ms.locfileid: "60844210"
---
# <a name="create-a-new-pin-policy-in-skype-for-business-server"></a>新しい PIN ポリシーを作成Skype for Business Server
 
**概要:** 新しい PIN ポリシーを作成します。Skype for Business Server。
  
[PIN ポリシー]**ページを使用** して、IP Phone を使用してユーザーに接続しているユーザーに個人識別番号 (PIN) 認証Skype for Business提供できます。 PIN 認証を使用するには、Web サービス設定で [**PIN 認証を有効にする**] が選択されていることを確認してください。
  
ユーザーレベルまたはサイトレベルの PIN ポリシーを作成するには、次の手順を実行します。 
  
### <a name="to-create-a-user-or-site-pin-policy"></a>ユーザーまたはサイトの PIN ポリシーを作成するには

1.  RTCUniversalServerAdmins グループのメンバーである (または同等のユーザー権限を持つ) ユーザー アカウント、または CsServerAdministrator または CsAdministrator 役割に割り当てられているユーザー アカウントから、Skype for Business Server を展開したネットワーク内の任意のコンピューターにログオンします。
    
2. ブラウザー ウィンドウを開き、管理者 URL を入力して[コントロール パネル] Skype for Business Server開きます。 
    
3. 左側のナビゲーション バーで [**セキュリティ**] をクリックし、[**PIN ポリシー**] をクリックします。
    
4. [**PIN ポリシー**] ページで [**新規**] をクリックして、次のどちらかを実行します。
    
   - ユーザーレベルのポリシーを作成するには、[**ユーザー ポリシー**] をクリックします。 [**新しい PIN ポリシー**] の [**名前**] に、ポリシーを説明する名前を入力します。
    
   - サイトレベルのポリシーを作成するには、[**サイト ポリシー**] をクリックします。 [**サイトの選択**] 検索フィールドに、ポリシーを作成するサイトの名前または名前の一部を入力します。 サイトの結果一覧で対象のサイトをクリックして、[**OK**] をクリックします。
    
5. [**説明**] フィールドに、PIN ポリシーの説明を入力します。
    
6. [**最小 PIN サイズ**] フィールドで、許可する PIN の最小サイズを入力または選択します。 既定の最小サイズは 5 桁です。
    
7. ユーザーがロックアウトされるまでに許可される最大ログオン試行回数を指定できるようにするには、[**最大ログオン試行回数を指定する**] チェック ボックスをオンにします。 このオプションをオンにしない場合、許可される最大試行回数は、PIN の桁数に応じて自動的に決定されます。 既定では、最大試行回数は自動的に決定されます。
    
8. [**最大ログオン試行回数を指定する**] チェック ボックスをオンにした場合は、[**最大ログオン試行回数**] に許可するログオンの最大試行回数を入力または選択します。
    
9. PIN の有効期限を設定するには、[**PIN の有効期限を有効にする**] チェック ボックスをオンにします。 このオプションをオンにしない限り、PIN が期限切れになることはありません。 既定では、PIN に有効期限はありません。
    
10. [**PIN の有効期限を有効にする**] チェック ボックスをオンにした場合は、[**PIN の有効期限 (日数)**] で、PIN の有効期限が切れるまでの日数を入力または選択します。
    
11. [**PIN 履歴の数**] に、PIN の数を入力します。作成した PIN の数がこの数を超えると、PIN を再利用できます。 既定では、ユーザーは自分の PIN を再利用できます。
    
12. PIN の数字の一般的なパターン ("1234" や "8888" など) を許可するには、[共通パターンを許可する] チェック **ボックスをオン** にします。 このオプションをオンにしない場合は、複雑な数字パターンのみが許可されます。 既定では、複雑なパターンの数字のみが許可されます。
    
    > [!IMPORTANT]
    > 共通のパターンは許可しないことをお勧めします。 
  
13. [**確定**] をクリックします。
    

