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
description: このトピックでは、Skype for Business Server 2015、2015 年 11 月の累積的な更新プログラムで回線共有機能 (SLA) を計画する方法について説明します。
ms.openlocfilehash: d7fa13b36c232e37c79e8509de71b4ac29ceff72
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49813347"
---
# <a name="plan-for-shared-line-appearance-in-skype-for-business-server-2015"></a>Skype for Business Server 2015 での回線共有機能の計画
 
このトピックでは、Skype for Business Server 2015、2015 年 11 月の累積的な更新プログラムで回線共有機能 (SLA) を計画する方法について説明します。 
  
回線共有機能は、共有番号と呼ばれる特定の番号で複数の通話を処理する Skype for Business の機能です。 SLA では、エンタープライズ ボイスが有効な Skype for Business ユーザーを複数の回線で共有番号として構成し、複数の通話に応答できます。 通話は実際には共有番号で受信されません。代わりに、共有番号の代理人として機能するユーザーに転送されます。 任意の代理人が通話を受け取る一方で、残りの代理人は電話で通話を受け取ったユーザーと、その結果ビジーになった回線に関する通知を受け取ります。 回線数と代理人の両方が、SLA の共有番号に対して構成できます。 また、BusyOption (すべての回線がビジー状態の場合に行う処理) や MissedCallOption (どの代理人も通話を受けない場合) などの高度なオプションも、共有番号に対して構成できます。
  
SLA は、次の電話デバイスでのみサポートされます (コンピューター、携帯電話、その他のデバイスの Skype for Business クライアントではサポートされていません)。 
  
- Polycom VVX300 とファームウェア更新プログラム 5.4.1
    
- Polycom VVX400 とファームウェア更新プログラム 5.4.1
    
- Polycom VVX500 とファームウェア更新プログラム 5.4.1
    
- Polycom VVX600 とファームウェア更新プログラム 5.4.1
    
SLA は、2015 年 11 月の累積的な更新プログラムである Skype for Business Server の新機能です。 
  
SLA の展開の詳細については [、「Deploy Shared Line Appearance in Skype for Business Server 2015」を参照](../../deploy/deploy-enterprise-voice/deploy-shared-line-appearance.md)してください。
  
## <a name="feature-list"></a>機能リスト

SLA グループを設定すると、次の操作が可能です。
  
- グループ内のすべての代理人は、同じ共有番号への着信呼び出しに応答できます。 通話は、PSTN ベースまたは SIP ベースの場合があります。
    
- 代理人は通話を保留して受け取る場合があります。
    
- 代理人は、SLA グループ外の番号に通話を転送できます。
    
- 代理人は、共有番号に現在の通話数を確認し、それらの各通話の状態を表示できます。
    
- 共有番号の同時通話の最大数を構成できます。 また、この最大数に達した後に追加の呼び出しを処理する方法を設定できます。 余分な通話は、ビジー信号で拒否するか、代替番号に転送するか、ボイス メールに転送することができます。
    
- 見つからない通話 (一定時間が過ごした後に呼び出しが取り出されない) の処理方法を構成できます。 グループ ID のボイス メールを有効にした場合、欠場した通話は自動的にボイス メールに移動します。 グループ ID (共有番号) に対してボイス メールを有効にしていない場合は、ビジー信号で拒否される、代替番号に転送する、切断された通話を選択できます。
    

