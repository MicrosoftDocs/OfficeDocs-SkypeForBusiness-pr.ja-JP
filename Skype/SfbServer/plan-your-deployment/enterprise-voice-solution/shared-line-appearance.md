---
title: Skype for Business Server 2015 の回線共有機能の計画
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
description: このトピックでは、Skype for Business Server 2015、2015年11月の累積更新プログラムで共有線の外観 (SLA) を計画する方法について説明します。
ms.openlocfilehash: 14f0f6cbd163ecff42543d3ad57bed0020434cfb
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41802437"
---
# <a name="plan-for-shared-line-appearance-in-skype-for-business-server-2015"></a>Skype for Business Server 2015 の回線共有機能の計画
 
このトピックでは、Skype for Business Server 2015、2015年11月の累積更新プログラムで共有線の外観 (SLA) を計画する方法について説明します。 
  
共有された線の外観は、共有番号と呼ばれる特定の電話番号で複数の通話を処理するための Skype for Business の機能です。 SLA では、エンタープライズボイス対応 Skype for Business のユーザーを、複数の回線を使って複数の通話に応答する共有番号として構成できます。 実際には共有番号で通話を受信するのではなく、共有番号の代理人として機能するユーザーに通話が転送されます。 いずれかの代理人が通話に応答すると、残りの代理人は誰が通話に応答したか、またその結果としてどの回線が通話中になったかを示す通知を自分の電話で受け取ります。 SLA では、回線の番号と代理人の両方を共有番号に対して構成できます。 さらに、BusyOption (すべての回線が通話中のときに実行する処理) と MissedCallOption (通話に応答できる代理人がいない場合の処理) などの高度なオプションも共有番号に対して構成できます。
  
SLA は、次の電話デバイスでのみサポートされます (コンピューター、携帯電話、その他のデバイス上の Skype for Business クライアントではサポートされていません)。 
  
- Polycom VVX300 (ファームウェア更新プログラム 5.4.1 インストール済み)
    
- Polycom VVX400 (ファームウェア更新プログラム 5.4.1 インストール済み)
    
- Polycom VVX500 (ファームウェア更新プログラム 5.4.1 インストール済み)
    
- Polycom VVX600 (ファームウェア更新プログラム 5.4.1 インストール済み)
    
SLA は、2015年11月の累積更新プログラムである、Skype for Business Server の新機能です。 
  
SLA の展開の詳細については、「[Deploy Shared Line Appearance in Skype for Business Server 2015](../../deploy/deploy-enterprise-voice/deploy-shared-line-appearance.md)」を参照してください。
  
## <a name="feature-list"></a>機能リスト

SLA グループをセットアップすると次のことが可能になります。
  
- グループ内のすべての代理人が同じ共有番号への着信通話に応答できます。PSTN ベースまたは SIP ベースの通話を利用できます。
    
- 代理人は、通話に応答することも保留にすることもできます。
    
- 代理人は、SLA グループの外部の番号に通話を転送できます。
    
- 代理人は、現在の共有番号上の通話数と、それらの各通話のステータスを表示できます。
    
- 共有番号で受信する通話の最大数を構成できます。この最大数に達した後にかかってきた通話の処理方法も設定できます。その後の通話に対しては、話中音を流すか、代替番号に転送するか、ボイス メールに転送できます。
    
- 不在着信 (一定の時間が経過しても応答されなかった通話) の処理方法を構成できます。グループ ID のボイス メールを有効にした場合、不在着信は自動的にボイス メールに転送されます。グループ ID (共有番号) のボイス メールを有効にしない場合、不在着信に対して話中音を流すか、代替番号に転送するか、切断するかを選ぶことができます。
    

