---
title: Skype for Business を使用してプライベート電話回線を計画する
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 9cc4f9e1-7b7a-4699-bd05-f16669ef2d21
description: Skype for Business Server のプライベート (セカンダリ) 電話回線のエンタープライズ VoIP。
ms.openlocfilehash: 0ae62c4ee56a16583106c89b5ca1b190ee242e2c
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49813597"
---
# <a name="plan-for-private-telephone-lines-with-skype-for-business"></a>Skype for Business を使用してプライベート電話回線を計画する
 
Skype for Business Server のプライベート (セカンダリ) 電話回線のエンタープライズ VoIP。
  
Skype for Business Server を使用すると、プライマリ電話回線に加えて、2 つ目のプライベート電話回線をユーザーに提供できます。 プライベート電話回線は、多くの場合、役員や直接受信できる非公開の電話番号が必要なユーザーに割り当てられます。
  
プライベート電話回線は、Skype for Business Server 管理シェルでのみ構成できます。 Skype for Business Server コントロール パネルを使用してプライベート電話回線を構成することはできません。 プライベート電話回線は、Skype for Business Server の展開でのみ構成し、混在展開では構成しない必要があります。
  
## <a name="characteristics-of-private-telephone-lines"></a>プライベート電話回線の特徴

2 つ目のプライベート電話回線の概念は基本的に単純ですが、プライベート回線の特性と、ユーザーのプライマリ電話回線と類似する方法と異なる方法を理解することが重要です。
  
### <a name="general-characteristics-of-private-telephone-lines"></a>プライベート電話回線の一般的特徴

- ユーザーに割り当てることができるプライベート電話回線は 1 つのみです。
    
- プライベート電話回線が割り当てられたユーザーには、ボイス メール用メールボックスは 1 つのみ設定され、不在着信通知は 1 つの電子メール アドレスに通知されます。
    
- プライベート電話回線が割り当てられたユーザーに、2 番目の SIP アドレスは割り当てられません。また、セカンダリのプライベート電話回線によって、ユーザーにネットワーク上の 2 番目のプレゼンス (2 番目のインスタント メッセージング ID など) は付与されません。 
    
- プライベート電話回線は、内部設置型展開でのみ使用できます。 Skype for Business Server のホスト型展開では使用できません。
    
### <a name="how-private-telephone-lines-differ-from-primary-telephone-lines"></a>プライベート電話回線とプライマリ電話回線の相違点

- プライベート電話回線の電話番号は、電話帳や Active Directory ドメイン サービスから得られる連絡先リストには表示されません。
    
- プライベート電話回線では、通話転送、チーム呼び出し、委任、チーム リング、グループ通話ピックアップ、応答グループ アプリケーションの機能は使用できません。
    
- プライベート電話回線の呼び出しには特別な呼び出し音が設定され、呼び出しのシステム通知により、プライベート番号に着信通話があることがユーザーに通知されます。
    
- プライベート電話回線の呼び出しは、常に直接行われます。 "応答不可" ルールには従いません。
    
- プライベート電話回線は着信のみで、発信通話に使用することはできません。 プライベート電話回線を使用しているユーザーが通話を行う場合、その通話はユーザーのプライマリ電話回線から発信され、ユーザーの名前やユーザーのプライマリ電話番号を呼び出し元から隠すのではありません。
    
### <a name="how-private-telephone-lines-are-similar-to-primary-telephone-lines"></a>プライベート電話回線とプライマリ電話回線の類似点

- プライベート電話回線の呼び出しで応答のなかったものは、プライマリ電話回線のものと同じボイス メール用受信ボックス (ボイス メールが有効になっている場合) にルーティングされます。
    
- コール パークとコール ピックアップは、ユーザーのプライマリ電話回線とまったく同じ方法でプライベート電話回線で動作します。
    
- ユーザーのプライマリ電話回線で同時呼び出しを有効にすると、プライベート電話回線でも有効になります。
    
- プライベート電話回線の電話番号は、ユーザーのプライマリ電話回線の電話番号と同じ方法で通話詳細レコードに記録されますが、プライベート電話番号として表示されます。
    
- ユーザーがプライベート電話回線で通話に応答すると、その通話はユーザーのプライマリ電話回線での通話と同じように処理されます。 たとえば、プライベート電話回線で通話を受信したユーザーが通話を転送したり、他のユーザーを電話会議に招待したりすると、そのユーザーの名前が Skype for Business に表示され、ユーザーのプライマリ電話回線の電話番号が発信者番号に表示されます。
    
- ユーザーは、プライマリ電話回線と同じ方法で、プライベート電話回線からの通話を切り替える (応答する前に、携帯電話や自宅の電話などの別の宛先に通話をリダイレクトする) ことができます。 
    
    > [!NOTE]
    > プライベート番号の呼び出しが別の電話番号にルーティングされた場合、その別の電話番号でプライベート電話回線の電話番号を使用できるようになり、その番号のログを表示できます。 
  
    > [!NOTE]
    > 電話会議からプライベート電話回線への通話では、着信システム通知にプライベート回線は表示しません。
  
## <a name="administering-private-telephone-lines"></a>プライベート電話回線の管理

プライベート電話回線の作成および管理の技術的な側面に加えて、プライベート電話回線用の回線管理手順を設定する必要があります。これには、組織内のプライベート番号の対象ユーザー向けのポリシーの指定、それらのユーザーとその電話番号の一覧の作成および管理、役員のプライベート電話帳の作成、ユーザー トレーニングの調整、関連する作業などがあります。
  
> [!NOTE]
> プライベート電話回線は、Active Directory にユーザー オブジェクトの msRTCSIP-PrivateLine 属性として格納されます。既定では、Authenticated Users グループのメンバーは、この属性に対して読み取りアクセスを持ちます。 
  
### <a name="assigning-telephone-numbers"></a>電話番号の割り当て

 プライベート電話回線を必要とする新規ユーザーのアカウントは、Skype for Business Server コントロール パネルまたは Skype for Business Server 管理シェルを使用して、プライベート電話回線のないアカウントと同じ方法で作成されます。
  
Skype for Business Server 管理シェル で **Set-CsUser** コマンドレットを使用して、ユーザーのプライベート電話回線に電話番号を割り当てる (例: **Set-CsUser -Identity "sip:joe@contoso.com" -PrivateLine "Tel:+14255551212"**)。
  
プライベート電話回線の電話番号は、3 ~ 15 の数字で、先頭に "TEL:" プレフィックスを付けする必要があります。 組織で市外局番や国/地域コードに Direct Inward Dialing を使用している場合、その市外局番や国/地域コードを指定できます。 
  
コマンドレットと Skype for Business Server 管理シェルの詳細については、Skype for Business Server 管理シェルのドキュメントを参照してください。
  
### <a name="private-telephone-lines-in-mixed-deployments"></a>混在環境におけるプライベート電話回線

プライベート電話回線は、Skype for Business Server または Lync Server 2013 の展開にのみ構成する必要があります。 以前のバージョンの Lync Server を実行しているサーバーがある展開では、以前のバージョンのユーザーがプライベート電話回線を呼び出しようとすると、サーバーがプライベート電話回線で番号の逆引き参照を実行できないので、通話のルーティングが失敗します。
  

