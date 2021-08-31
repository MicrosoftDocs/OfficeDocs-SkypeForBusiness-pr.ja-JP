---
title: '[通話の計画] 作業時間内の作業Skype for Business Server'
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: a33ec637-9ac8-4cb7-b3b2-88d432efc078
description: Skype for Business Server で通話の計画を立て、Skype for Business と PBX 電話システムとの統合を可能にし、ユーザーが pbx 電話を制御するために Skype for Business を使用できます。
ms.openlocfilehash: bc2a20741f4f89d4a535b9aa0278fea85a8f44c6
ms.sourcegitcommit: 15e90083c47eb5bcb03ca80c2e83feffe67646f2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/30/2021
ms.locfileid: "58732586"
---
# <a name="plan-for-call-via-work-in-skype-for-business-server"></a>[通話の計画] 作業時間内の作業Skype for Business Server
 
Skype for Business Server で通話の計画を立て、Skype for Business と PBX 電話システムとの統合を可能にし、ユーザーが pbx 電話を制御するために Skype for Business を使用できます。
  
 **Call Via Work** は、既存の PBX 電話システムSkype for Business Serverソリューションを統合Skype for Business新しい機能です。 [仕事による通話] が有効になっているユーザーは、展開内Skype for Business外部ユーザーのどちらかで、別のユーザーを呼び出す方法をクリックできます。 通話は、ユーザーの PBX 電話を使用して完了します。 これにより、PBX 電話を持つユーザーは、リッチ メッセージの会話にオーディオSkype for Businessできます。 以前のバージョンの Lync Server リモート呼び出し制御は、ユーザーが Lync Server で PBX 電話を制御できる機能でした。 このSkype for Business Serverは、Call Via Work に置き換えされています。
  
仕事による通話では、PBX 電話ユーザーに対して次の操作を有効にします。
  
- PBX 電話を介して提供される音声を使用した、通話のクリックエクスペリエンス。
    
- プレゼンス、ユーザー検索、IM 統合-たとえば、IM セッション内の 2 人の Call Via Work ユーザーは、PBX 電話を介して提供される音声を使用して、セッションにオーディオを追加できます。
    
- IM、アプリケーション共有、およびファイル転送を Call Via Work 呼び出しに追加する機能。
    
- 会議参加機能を 1 回クリックする
    
## <a name="how-it-works"></a>メカニズム

Call Via Work は、PBX システムと Skype for Business Server 展開の間のバック to バック ユーザー エージェント (B2BUA) としてユニファイド コミュニケーション Web API (UCWA) を使用します。そのため、pbx システムに Skype for Business Server を接続するためにコンピューターでサポートされる通信アプリケーション (CSTA) ゲートウェイは必要とされません。 UCWA は、以前のバージョンの Lync Server で導入されたサービスで、モバイル クライアントと Web クライアントとの接続を有効にし、すべてのフロント エンド サーバーに自動的にインストールされます。
  
### <a name="call-workflow-for-a-call-via-work-call"></a>作業時間による通話の呼び出しワークフロー

次に、ユーザーが [通話経由の作業] を有効にした場合に、Skype for Business Serverを使用して通話を行う方法を示します。
  
![通話の通話中の手順を表示します。最初に、呼び出し元がクライアント内のユーザーを呼び出Skype for Businessします。その後、UCWA は発信者の電話を呼び出します。 発信者が電話を受け取ると、受信者が呼び出されます。](../../media/050e88ed-e18e-40c0-84d5-b17fe40c305a.jpg)
  
1. ユーザーはクライアントでユーザーをSkype for Businessし、電話アイコンをクリックして呼び出します。 または、IM 会話中に、ユーザーがクリックして、セッションを行っているユーザーを呼び出します。
    
2. 通話を行ったユーザーの PBX 電話が呼び出しを開始します。 この電話の発信者 ID には、通話経由通話を発信しているすべてのユーザーの発信者 ID に表示するために設定したグローバル電話番号が表示されます。 このグローバル電話番号は、1 人のユーザーの電話に対応する実際の電話番号ではありません。 その代わりに、これが自分の発信通話であり、同時に着信呼び出しが行なっていないことをユーザーに知らせたのは視覚的な信号です。 Call Via Work を展開する場合は、これらのユーザーにこのグローバル電話番号とそれが何を意味するのかを教育する必要があります。
    
3. 通話を行ったユーザーは、PBX 電話を受け取る。 Skype for Business呼び出し先への音声通話を開始します。 
    
4. 呼び出し先が応答すると、音声通話が開始されます。 2 人のユーザーが既に IM セッションを実行している場合は、続行できます。
    
### <a name="joining-a-conference-with-call-via-work"></a>仕事を通じて電話で会議に参加する

[仕事を経由して通話] ユーザーは、会議の URL をクリックして、スケジュールされた会議に参加できます。 Skype for Business会議サービスがユーザーのPBX 電話にダイヤルするまで、メッセージにダイヤルアウトを表示します。 次に、[作業時間を使用して通話] ユーザーが PBX 電話を受け取り、会議に参加します。
  
[作業時間を使用して通話]ユーザーは、[今すぐ会議] オプションを使用して会議Skype for Business会議を作成することもできます。 次に、ユーザーに [ダイヤルアウト] メッセージ **が表示** され、PBX の電話が呼び出されます。
  
[仕事を経由して通話] ユーザーは、会議ブリッジ番号を電話会議から呼び出すことによって、会議にダイヤルインSkype for Business。 会議 PIN が必要な場合、ユーザーは PBX 電話を使用して PIN を入力する必要があります。
  
### <a name="incoming-calls"></a>着信呼び出し

Call Via Work を有効にしたユーザーが Skype for Business 通話を受信すると、PBX 電話とユーザーの Skype for Business クライアントが同時に呼び出されます (ユーザーが同時呼び出しを設定している場合)。 ユーザーは、PBX の電話を受け取るか、または[通知の受信] をクリックして、Skype for Businessできます。 ユーザーがユーザーを使用して呼び出しを受けSkype for Business、通話のSkype for Businessウィンドウが開いたままです。 ただし、ユーザーが PBX 電話を受け取って通話を受け入れる場合は、Skype for Business 通知ウィンドウが閉じ、Skype for Business セッションが無く、PBX 電話を使用した音声通話のみになります。
  
[作業による通話] を有効にしたユーザーが PBX 呼び出しを受信すると、PBX の電話だけが呼び出されます。
  
## <a name="limitations-of-call-via-work"></a>仕事による通話の制限

Call Via Work は、ハードウェアのセットアップをほとんど必要としませんが、完全な通話またはリモート通話制御で使用できる機能と比較して制限エンタープライズ VoIP音声ソリューションです。 仕事経由の呼び出しには、次の制限があります。
  
- Call Via Work ユーザーが Call Via Work コールバック番号への通話転送を設定し、ユーザーがユーザーの電話番号でこのユーザーを会議に招待しようとすると、招待はユーザーに届かない。 電話番号ではなく名前をクリックして、参加者を会議に招待するユーザーを教育する必要があります。 
    
- 拡張 911 機能と悪意のある呼び出しトレースは、通話経由の通話中は利用できません。
    
- Call Via Work で有効なユーザーは、委任、チーム通話、または応答グループの機能を使用できません。
    
- 通話のユーザーは、会議をSkype for Business、通話のミュートまたはミュート解除、通話の保留または転送、通話パークの使用を行う必要があります。
    
- ユーザーは、仕事で通話を使用して PBX ボイスメール メッセージにアクセスすることはできません。
    
- 通話のユーザーは、音声通話として開始されたセッションを、ビデオ、Powerpoint、ホワイトボード、One Note などの通信を含む共同作業会議にエスカレートできません。
    
- [仕事による通話] のユーザーは、2 人の通話にユーザーを追加できません。
    
- デスクフォンのペアリングまたは VDI プラグインのペアリングはサポートされていません。
    
- ユーザーが PBX 電話を使用して通話を行った場合または応答した場合 (および [Skype for Business] ウィンドウを使用しない場合、通話のログは表示されません。
    
- PBX システムで REFER with **Replaces** がサポートされていない場合は、次の動作が発生します。 [仕事による通話] 通話中に、ユーザーが PBX 電話 から継続的な通話を転送した場合、通話ウィンドウが [通話] ウィンドウSkype for Businessなくなります。 ユーザーが呼び出しウィンドウを閉じると、転送先と転送先の間の呼び出しが終了します。 
    
## <a name="prerequisites-for-call-via-work"></a>仕事による通話の前提条件

すべてのユーザーが [仕事を経由して通話] を有効にするには、前提条件を設定する必要があります。 これらの前提条件の詳細、およびユーザーによる通話を有効にする方法の手順については、「Deploy Call Via Work in Skype for Business Server [2015」を参照](../../deploy/deploy-call-via-work.md)してください。 
  
## <a name="see-also"></a>関連項目

[リモート通話制御の計画を立Skype for Business](remote-call-control.md)
  
[2015 年 3 月に作業を通じて通話Skype for Business Server展開する](../../deploy/deploy-call-via-work.md)

