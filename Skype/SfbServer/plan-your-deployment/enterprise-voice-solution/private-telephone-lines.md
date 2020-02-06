---
title: Skype for Business でのプライベート電話回線の計画
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
description: Skype for Business Server Enterprise Voice でのプライベート (セカンダリ) 電話回線の計画。
ms.openlocfilehash: 001a83e4bd81f0f47546f51f1d4993c6b1cec4bf
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41802567"
---
# <a name="plan-for-private-telephone-lines-with-skype-for-business"></a>Skype for Business でのプライベート電話回線の計画
 
Skype for Business Server Enterprise Voice でのプライベート (セカンダリ) 電話回線の計画。
  
Skype for Business Server では、2番目のプライベート電話回線と、お客様のプライマリ電話回線をユーザーに提供することができます。 プライベート電話回線は、多くの場合、役員や直接受信できる非公開の電話番号が必要なユーザーに割り当てられます。
  
プライベート電話回線を構成するには、Skype for Business Server 管理シェルを使用する必要があります。 Skype for Business Server コントロールパネルでプライベート電話回線を構成することはできません。 プライベート電話回線は、混在展開ではなく、Skype for Business Server の展開でのみ構成する必要があります。
  
## <a name="characteristics-of-private-telephone-lines"></a>プライベート電話回線の特徴

第2のプライベート電話回線という概念は基本的に単純ですが、プライベート回線の特性と、ユーザーの主要な電話回線との類似および異なる方法を理解しておくことが重要です。
  
### <a name="general-characteristics-of-private-telephone-lines"></a>プライベート電話回線の一般的特徴

- ユーザーに割り当てることができるプライベート電話回線は 1 つのみです。
    
- プライベート電話回線が割り当てられたユーザーには、ボイス メール用メールボックスは 1 つのみ設定され、不在着信通知は 1 つの電子メール アドレスに通知されます。
    
- プライベート電話回線が割り当てられたユーザーに、2 番目の SIP アドレスは割り当てられません。また、セカンダリのプライベート電話回線によって、ユーザーにネットワーク上の 2 番目のプレゼンス (2 番目のインスタント メッセージング ID など) は付与されません。 
    
- プライベート電話回線は、内部設置型展開でのみ使用できます。 Skype for Business Server のホスト型展開では使用できません。
    
### <a name="how-private-telephone-lines-differ-from-primary-telephone-lines"></a>プライベート電話回線とプライマリ電話回線の相違点

- プライベート電話回線の電話番号は、電話帳や Active Directory ドメイン サービスから得られる連絡先リストには表示されません。
    
- プライベート電話回線では、着信の転送、チーム呼び出し、委任、チーム呼び出し、グループ通話ピックアップ、および応答グループ アプリケーションの機能は使用できません。
    
- プライベート電話回線の呼び出しには特別な呼び出し音が設定され、呼び出しのシステム通知により、プライベート番号に着信通話があることがユーザーに通知されます。
    
- プライベート電話回線の呼び出しは、常に直接行われます。"応答不可" ルールには従いません。
    
- プライベート電話回線は着信のみで、発信通話に使用することはできません。 専用電話回線を使っているユーザーが通話を発信すると、通話はユーザーのプライマリ電話回線から発信され、ユーザーの名前またはユーザーの主要な電話番号は、呼び出し元からは非表示になりません。
    
### <a name="how-private-telephone-lines-are-similar-to-primary-telephone-lines"></a>プライベート電話回線とプライマリ電話回線の類似点

- プライベート電話回線の呼び出しで応答のなかったものは、プライマリ電話回線のものと同じボイス メール用受信ボックス (ボイス メールが有効になっている場合) にルーティングされます。
    
- 電話会議では、ユーザーのプライマリ電話回線とまったく同じ方法で、専用の電話回線を使って、集配作業を行うことができます。
    
- ユーザーのプライマリ電話回線で同時呼び出しが有効になっている場合は、プライベート電話回線でも有効になります。
    
- プライベート電話回線の電話番号は、ユーザーの主要な電話回線の電話番号と同じ方法で、通話の詳細レコードに記録されますが、これはプライベート電話番号であることを示しています。
    
- ユーザーがプライベート電話回線で着信に応答すると、その通話はユーザーのプライマリ電話回線での通話と同じように扱われます。 たとえば、プライベート電話回線で通話を受信したユーザーが通話を転送したり、会議通話に他のユーザーを招待したりすると、そのユーザーの名前が Skype for Business に表示され、ユーザーのプライマリ電話回線の電話番号が発信者番号認識に表示されます。
    
- ユーザーは、プライマリ電話回線と同じ方法で、プライベート電話回線からの通話を切り替える (応答する前に、携帯電話や自宅の電話などの別の宛先に通話をリダイレクトする) ことができます。 
    
    > [!NOTE]
    > プライベート番号の呼び出しが別の電話番号にルーティングされた場合、その別の電話番号でプライベート電話回線の電話番号を使用できるようになり、その番号のログを表示できます。 
  
    > [!NOTE]
    > 電話会議からプライベート電話回線への通話には、着信システム通知に*プライベートな線*のマークは表示されません。
  
## <a name="administering-private-telephone-lines"></a>プライベート電話回線の管理

プライベート電話回線の作成および管理の技術的な側面に加えて、プライベート電話回線用の回線管理手順を設定する必要があります。これには、組織内のプライベート番号の対象ユーザー向けのポリシーの指定、それらのユーザーとその電話番号の一覧の作成および管理、役員のプライベート電話帳の作成、ユーザー トレーニングの調整、関連する作業などがあります。
  
> [!NOTE]
> プライベート電話回線は、Active Directory にユーザー オブジェクトの msRTCSIP-PrivateLine 属性として格納されます。既定では、Authenticated Users グループのメンバーは、この属性に対して読み取りアクセスを持ちます。 
  
### <a name="assigning-telephone-numbers"></a>電話番号の割り当て

 プライベート電話回線を必要とする新しいユーザーのアカウントは、Skype for Business Server コントロールパネルまたは Skype for Business Server Management Shell を使用して、プライベート電話回線のないアカウントと同じ方法で作成されます。
  
Skype for Business Server 管理シェルの [ **set-CsUser** ] コマンドレットを使用して、ユーザーのプライベート電話回線に電話番号を割り当てます。たとえば、" **Sip:joe@contoso.com"-PrivateLine "Tel: + 14255551212"** のように設定します。
  
プライベート電話回線の電話番号には、3 ~ 15 個の番号を使用できます。また、前に "TEL:" プレフィックスを指定する必要があります。 組織で市外局番や国/地域コードに Direct Inward Dialing を使用している場合、その市外局番や国/地域コードを指定できます。 
  
コマンドレットと Skype for Business Server Management Shell の詳細については、「Skype for Business Server 管理シェルのドキュメント」を参照してください。
  
### <a name="private-telephone-lines-in-mixed-deployments"></a>混在環境におけるプライベート電話回線

専用の電話回線は、Skype for Business Server または Lync Server 2013 の展開用にのみ構成する必要があります。 以前のバージョンの Lync Server を実行しているサーバーがある展開では、以前のバージョンのユーザーがプライベート電話回線に電話をかけようとしたときに、サーバーがプライベート電話回線で逆引き番号参照を実行できないため、通話のルーティングが失敗します。
  

