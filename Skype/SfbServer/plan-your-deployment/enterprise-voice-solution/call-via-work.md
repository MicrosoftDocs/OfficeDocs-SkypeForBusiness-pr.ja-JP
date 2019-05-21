---
title: Skype for Business Server での勤務先での通話の計画
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: a33ec637-9ac8-4cb7-b3b2-88d432efc078
description: Skype for business Server を使った skype for business Server での通話の計画。 skype for business と PBX 電話システムとの統合を有効にし、ユーザーが Skype for Business を使用して PBX 電話を制御できるようにします。
ms.openlocfilehash: b2f0e57a33f6e194dc981b623a641850ed3c8de5
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34277028"
---
# <a name="plan-for-call-via-work-in-skype-for-business-server"></a>Skype for Business Server での勤務先での通話の計画
 
Skype for business Server を使った skype for business Server での通話の計画。 skype for business と PBX 電話システムとの統合を有効にし、ユーザーが Skype for Business を使用して PBX 電話を制御できるようにします。
  
 [勤務先での**通話**は、Skype For business Server の新機能です。 skype for business ソリューションと既存の PBX 電話システムとの統合を可能にします。 勤務先からの通話が有効になっているユーザーは、[Skype for Business] をクリックして、展開または外部ユーザーのいずれかで別のユーザーに電話をかけることができます。 この通話は、ユーザーの PBX 電話を使用して実現されます。 これにより、PBX 電話を使用するユーザーは、豊富な Skype for Business の会話に音声を含めることができます。 以前のバージョンの Lync Server リモート通話コントロールは、ユーザーが Lync Server を使って PBX 電話を制御できるようにする機能です。 Skype for Business Server では、この機能は勤務先からの通話に置き換えられました。
  
勤務先での通話 PBX 電話のユーザーに対して次の機能を有効にします。
  
- PBX 電話で提供される音声を使用した、クリック通話操作。
    
- プレゼンス、ユーザー検索、IM の統合: たとえば、IM セッションで [勤務先] の2回の通話では、PBX 電話経由で提供されたオーディオを使って、そのセッションに音声を追加できます。
    
- 通話に IM、アプリケーション共有、ファイル転送を追加する機能。
    
- ワンクリックでの会議参加機能
    
## <a name="how-it-works"></a>メカニズム

[勤務先での通話] PBX システムと Skype for Business Server の展開の間のバックツーバックユーザーエージェント (B2BUA) としてユニファイドコミュニケーション Web API (UCWA) を使用します。これにより、コンピューターでサポートされている通信アプリケーション (CSTA) ゲートウェイは接続する必要がなくなります。お使いの PBX システムを搭載した Skype for Business Server。 UCWA は、モバイルおよび web クライアントとの接続を可能にするために、以前のバージョンの Lync Server で導入されたサービスであり、すべてのフロントエンドサーバーに自動的にインストールされます。
  
### <a name="call-workflow-for-a-call-via-work-call"></a>勤務先から通話のワークフローを呼び出す

次の例は、勤務先のユーザーが Skype for Business Server を使って通話を発信する方法を示しています。
  
!["勤務先から通話" の通話中のステップを示しています。まず、発信者が Skype for Business クライアントで誰かにクリックで発信し、次に、UCWA が発信者の電話を鳴らします。発信者が電話を取ると、受信者が呼び出されます](../../media/050e88ed-e18e-40c0-84d5-b17fe40c305a.jpg)
  
1. ユーザーは、Skype for Business クライアントでユーザーを選択し、電話のアイコンをクリックして通話を発信します。 または、IM 会話中にクリックして、セッションを共有しているユーザーに電話をかけます。
    
2. 電話をかけたユーザーの PBX 電話が呼び出しを開始します。 この電話の発信者番号は、[勤務先] で通話を発信しているすべてのユーザーの発信者番号認識に設定したグローバル電話番号を示しています。 このグローバル電話番号は、個人の電話に応じた実際の電話番号ではありません。 これは、ユーザー自身が発信した電話であり、着信ではないことを同時に相手に知らせる視覚的信号です。 職場で通話を展開する場合は、このグローバル電話番号とその意味についてユーザーを教育する必要があります。
    
3. 電話をかけたユーザーは自分の PBX 電話を取ります。 次に、Skype for Business から呼び出し先への音声通話が開始されます。 
    
4. 呼び出し先が応答すると、音声通話が開始します。2 人のユーザーが既に IM セッションを開始している場合は、これを継続できます。
    
### <a name="joining-a-conference-with-call-via-work"></a>"勤務先から通話" を使用した会議への参加

職場ユーザーからの通話は、会議の URL をクリックして、スケジュールされた会議に参加することができます。 Skype for Business は、会議サービスがユーザーの PBX 電話にダイヤルするまで、メッセージ**へのダイヤルアウト**を示します。 職場ユーザーからの通話は、PBX 電話を選び、会議に参加します。
  
職場ユーザーからの通話では、Skype for Business の [**今すぐ会議**] オプションを使用して、[今すぐ会議] 会議を作成することもできます。 続いてユーザーに「**〜さんにダイヤルしています**」というメッセージが表示され、PBX 電話が呼び出されます。
  
職場ユーザーからの通話では、Skype for Business 内から会議ブリッジ番号に電話をかけて会議にダイヤルインすることもできます。 会議 PIN が必要な場合、ユーザーはその PBX 電話を使用して、PIN を入力する必要があります。
  
### <a name="incoming-calls"></a>着信通話

ユーザーが [勤務先からの通話] を有効にすると、Skype for Business の通話が受信され、PBX 電話とユーザーの Skype for Business クライアントがすべて同時に着信します (ユーザーが同時呼び出しを設定している場合)。 ユーザーは、PBX 電話を選ぶか、Skype for Business の通知で [**承諾**] をクリックすることで、通話を受けることができます。 ユーザーが Skype for Business を使って通話を受け入れた場合、通話の Skype for business ウィンドウは開いたままになります。 ただし、ユーザーが PBX 電話を使って通話を受けた場合は、Skype for Business の通知ウィンドウが閉じ、PBX 携帯電話での音声通話のみが表示されます。
  
勤務先からの通話が有効になっているユーザーが PBX 通話を受信した場合は、PBX 電話のみが着信します。
  
## <a name="limitations-of-call-via-work"></a>勤務先での通話の制限

[勤務先からの通話] は、わずかなハードウェアのセットアップが必要ですが、完全なエンタープライズ Voip またはリモート通話コントロールで利用できる機能との制限があります。 勤務先での通話には、次のような制限があります。
  
- 勤務先からの通話で、勤務先のコールバック番号を使って通話への通話転送を設定した場合、ユーザーの電話番号による会議にこのユーザーを招待しようとしても、招待はユーザーに届かなくなります。 参加者を会議に招待するには、電話番号ではなく名前をクリックするように、ユーザーに伝える必要があります。 
    
- 拡張された911機能と悪意のある通話の追跡は、勤務先の通話では利用できません。
    
- 職場での通話が有効になっているユーザーは、委任、チーム呼び出し、または応答グループの機能を使用できません。
    
- 勤務先からの通話のユーザーは、Skype for Business を使用して、会議の記録、通話のミュート/ミュート解除、通話の保留または転送、または通話パークの使用を行うことはできません。
    
- ユーザーは、PBX ボイスメールメッセージにアクセスするために勤務先から通話を使用することはできません。
    
- 勤務先からの通話のユーザーは、音声通話として開始されたセッションを、ビデオ、Powerpoint、ホワイトボード、または1つのノートなどのコミュニケーションを含む共同会議にエスカレートすることはできません。
    
- 勤務先からの通話のユーザーは、2人のユーザーとの通話により多くのユーザーを追加することはできません。
    
- 卓上電話のペアリングまたは VDI プラグイン ペアリングをサポートしていません。
    
- ユーザーが PBX 電話を使って通話に応答した場合 (Skype for Business ウィンドウを使用していない場合)、通話のログは記録されません。
    
- PBX システムが **REFER with Replaces** をサポートしていない場合は、次のように動作します。 勤務先の通話中に、ユーザーが PBX 携帯電話から進行中の通話を転送した場合、通話ウィンドウは Skype for Business ウィンドウに表示されなくなります。 ユーザーが通話ウィンドウを閉じると、転送先との間の通話が終了します。 
    
## <a name="prerequisites-for-call-via-work"></a>勤務先での通話の前提条件

勤務先から通話を発信できるようにするには、あらかじめいくつかの前提条件を設定しておく必要があります。 これらの前提条件について詳しくは、「 [Skype For Business Server 2015 で](../../deploy/deploy-call-via-work.md)の電話での通話の展開」をご覧ください。 
  
## <a name="see-also"></a>関連項目

[Skype for Business のリモート通話コントロールを計画する](remote-call-control.md)
  
[Skype for Business Server 2015 での "勤務先から通話" の展開](../../deploy/deploy-call-via-work.md)

