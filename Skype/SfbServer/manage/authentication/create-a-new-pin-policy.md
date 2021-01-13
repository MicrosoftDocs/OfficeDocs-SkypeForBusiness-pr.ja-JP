---
title: Skype for Business Server で新しい PIN ポリシーを作成する
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 8bdf0478-fe9f-4371-93ff-db39381a25db
description: '概要: Skype for Business Server で新しい PIN ポリシーを作成します。'
ms.openlocfilehash: b0d1be74e509fbaddfc59250f4f5ce05a2021260
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49828407"
---
# <a name="create-a-new-pin-policy-in-skype-for-business-server"></a>Skype for Business Server で新しい PIN ポリシーを作成する
 
**概要:** Skype for Business Server で新しい PIN ポリシーを作成します。
  
**[PIN** ポリシー] ページを使用して、IP 電話で Skype for Business に接続しているユーザーに暗証番号 (PIN) 認証を提供できます。 PIN 認証を使用するには、Web サービス設定で [**PIN 認証を有効にする**] が選択されていることを確認してください。
  
ユーザーレベルまたはサイトレベルの PIN ポリシーを作成するには、次の手順を実行します。 
  
### <a name="to-create-a-user-or-site-pin-policy"></a>ユーザーまたはサイトの PIN ポリシーを作成するには

1.  RTCUniversalServerAdmins グループのメンバーである (または同等のユーザー権限を持つ) ユーザー アカウントから、または CsServerAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、Skype for Business Server を展開したネットワーク内の任意のコンピューターにログオンします。
    
2. ブラウザー ウィンドウを開き、管理 URL を入力して Skype for Business Server コントロール パネルを開きます。 
    
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
    
12. PIN の一般的なパターン ("1234" や "8888" など) を許可するには、[共通パターンを許可する] チェック **ボックスをオン** にします。 このオプションをオンにしない場合は、複雑な数字パターンのみが許可されます。 既定では、複雑なパターンの数字のみが許可されます。
    
    > [!IMPORTANT]
    > 共通のパターンは許可しないことをお勧めします。 
  
13. [**確定**] をクリックします。
    

