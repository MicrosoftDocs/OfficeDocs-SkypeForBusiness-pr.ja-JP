---
title: Skype for Business Server 2015 での回線共有機能の計画
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/21/2016
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
ms.assetid: 6356aad4-700d-495c-8fc8-58eb1d4f6f18
description: このトピックを読んで、Skype for Business Server 2015、2015 年 11 月累積的な更新プログラムにおける回線共有機能 (SLA) を計画する方法を学びます。
ms.openlocfilehash: cabd5a9f6780371a8345bd95c5686829e74ad3c18e875ec85decf6ab0ca2f789
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2021
ms.locfileid: "54289725"
---
# <a name="plan-for-shared-line-appearance-in-skype-for-business-server-2015"></a>Skype for Business Server 2015 での回線共有機能の計画
 
このトピックを読んで、Skype for Business Server 2015、2015 年 11 月累積的な更新プログラムにおける回線共有機能 (SLA) を計画する方法を学びます。 
  
回線共有機能は、共有番号と呼ばれる特定の番号での複数の通話を処理するための Skype for Business の機能です。 回線共有機能は、エンタープライズ音声対応の Skype for Business ユーザーを、複数の回線を持つ共有番号として構成し、複数の通話に応答することができます。 共有番号にかかってきた通話は、実際には受信されず、共有番号の代理人であるユーザーに転送されます。 代理人であるユーザーが通話に応答することができ、他の代理人はどのユーザーが電話に応答したか、その結果どの回線がビジーになったかなどの通知を携帯電話で受信することができます。 回線共有機能では、回線数と代理人の両方が共有番号に構成可能です。 さらに、BusyOption (すべての回線がビジー状態の場合) やMissedCallOption (代理人が誰も通話に応答しない場合) などの詳細オプションを共有番号に構成することもできます。
  
回線共有機能は以下のモバイル デバイスでのみサポートされています (コンピューターや携帯電話などの Skype for Business クライアントではサポートされていません)。 
  
- ファームウェア更新プログラム 5.4.1 対応の Polycom VVX300
    
- ファームウェア更新プログラム 5.4.1 対応の Polycom VVX400
    
- ファームウェア更新プログラム 5.4.1 対応の Polycom VVX500
    
- ファームウェア更新プログラム 5.4.1 対応の Polycom VVX600
    
回線共有機能は、Skype for Business Server、2015 年 11 月累積的な更新プログラムの新機能です。 
  
回線共有機能の展開の詳細については、「[Skype for Business Server 2015 での回線共有機能の展開](../../deploy/deploy-enterprise-voice/deploy-shared-line-appearance.md)」を参照してください。
  
## <a name="feature-list"></a>機能一覧

回線共有機能グループを設定することにより、以下のことが可能になります。
  
- グループ内のすべての代理人は、同じ共有番号にかかってきた受信番号に応答することができます。 通話は PSTN ベースでも SIP ベースでも応答できます。
    
- 代理人は通話を保留したり、受信したりすることができます。
    
- 代理人は、回線共有機能グループ外の番号に通話を転送することができます。
    
- 代理人は、共有番号にかかってきている通話数や、それぞれの通話状態を確認することができます。
    
- 共有番号の最大同時通話数を構成することができます。 この最大値に達した後の追加通話を処理する方法についても設定できます。 最大値を超える通話は、ビジー信号で拒否したり、別の電話番号に転送したり、ボイスメールに転送したりすることができます。
    
- 不在着信 (一定時間を過ぎても通話に応答しない着信) の処理方法を構成できます。 グループ ID でボイスメールを有効にしている場合、不在着信は自動的にボイスメールに送信されます。 グループ ID (共有番号) でボイスメールを有効にしていない場合は、不在着信をビジー信号で拒否するか、別の番号に転送するか、切断するかを選択できます。
    

