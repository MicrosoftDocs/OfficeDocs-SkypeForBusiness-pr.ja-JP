---
title: 既存の PIN ポリシーを変更Skype for Business Server
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
ms.assetid: 517caaee-3349-4fa6-8d86-e4da3258a445
description: '概要: 既存の PIN ポリシーを変更Skype for Business Server。'
ms.openlocfilehash: 7770e34315dc0e407ecc4523fc133fce696d9c5b5eadba35979937761230b0cf
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2021
ms.locfileid: "54297343"
---
# <a name="modify-an-existing-pin-policy-in-skype-for-business-server"></a>既存の PIN ポリシーを変更Skype for Business Server
 
**概要:** 既存の PIN ポリシーを変更Skype for Business Server。
  
[PIN ポリシー]**タブを使用** して、IP Phone を使用してユーザーに接続しているユーザーに個人識別番号 (PIN) 認証Skype for Business提供できます。 PIN 認証を使用するには、Web サービス設定で [**PIN 認証を有効にする**] が選択されていることを確認してください。
  
ユーザー レベルまたはサイト レベルの PIN ポリシーを変更するには、次の手順に従います。 
  
### <a name="to-modify-an-existing-pin-policy"></a>既存の PIN ポリシーを変更するには

1.  RTCUniversalServerAdmins グループのメンバーである (または同等のユーザー権限を持つ) ユーザー アカウント、または CsServerAdministrator または CsAdministrator 役割に割り当てられているユーザー アカウントから、Skype for Business Server を展開したネットワーク内の任意のコンピューターにログオンします。
    
2. ブラウザー ウィンドウを開き、管理者 URL を入力して[コントロール パネル] Skype for Business Server開きます。 
    
3. 左側のナビゲーション バーで [**セキュリティ**] をクリックし、[**PIN ポリシー**] をクリックします。
    
4. [**PIN ポリシー**] ページでポリシーをクリックし、[**編集**] に続いて [**詳細の表示**] をクリックします。
    
5. [**PIN ポリシーの編集**] の [**最小 PIN サイズ**] で、許可する PIN の最小文字数を入力または選択します。 既定の最小サイズは 5 桁です。
    
6. ユーザーがロックアウトされるまでに許可される最大ログオン試行回数を指定できるようにするには、[**最大ログオン試行回数を指定する**] チェック ボックスをオンにします。 このオプションをオンにしない場合、許可される最大試行回数は、PIN の桁数に応じて自動的に決定されます。 既定では、最大試行回数は自動的に決定されます。
    
7. [**最大ログオン試行回数を指定する**] チェック ボックスをオンにした場合は、[**最大ログオン試行回数**] に許可するログオンの最大試行回数を入力または選択します。
    
8. PIN の有効期限を設定するには、[**PIN の有効期限を有効にする**] チェック ボックスをオンにします。 このオプションをオンにしない限り、PIN が期限切れになることはありません。 既定では、PIN に有効期限はありません。
    
9. [**PIN の有効期限を有効にする**] チェック ボックスをオンにした場合は、[**PIN の有効期限 (日数)**] で、PIN の有効期限が切れるまでの日数を入力または選択します。
    
10. [**PIN 履歴の数**] に、PIN の数を入力します。作成した PIN の数がこの数を超えると、PIN を再利用できます。 既定では、ユーザーは自分の PIN を再利用できます。
    
11. PIN に、連続番号や同じ数字の繰り返しなどよくあるパターンの番号を許可するには、[**共通のパターンの許可**] チェック ボックスをオンにします。 このオプションをオンにしない場合は、複雑な数字パターンのみが許可されます。 既定では、複雑なパターンの数字のみが許可されます。
    
    > [!IMPORTANT]
    > 共通のパターンは許可しないことをお勧めします。 
  
12. [**確定**] をクリックします。
    

