---
title: Plan for Call Via Work in Skype for Business Server
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
ms.assetid: a33ec637-9ac8-4cb7-b3b2-88d432efc078
description: Skype for Business と PBX 電話システムの統合が可能で、ユーザーが Skype for Business を使用して PBX 電話を制御できるような、Skype for Business Server での[通話から作業] の計画。
ms.openlocfilehash: e443a5d2709f1aca69ef200e72de43251cd16047
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49825877"
---
# <a name="plan-for-call-via-work-in-skype-for-business-server"></a>Plan for Call Via Work in Skype for Business Server
 
Skype for Business と PBX 電話システムの統合が可能で、ユーザーが Skype for Business を使用して PBX 電話を制御できるような、Skype for Business Server での[作業から通話] の計画。
  
 **Call Via Work** は、Skype for Business Server の新機能で、Skype for Business ソリューションを既存の PBX 電話システムと統合できます。 [仕事から通話] が有効なユーザーは、Skype for Business でクリックして、展開内または外部ユーザーのどちらかに別のユーザーに電話をかけできます。 通話は、ユーザーの PBX 電話を使用して完了します。 これにより、PBX 電話を使用するユーザーは、豊富な Skype for Business 会話にオーディオを含めできます。 以前のバージョンの Lync Server のリモート通話コントロールは、ユーザーが Lync Server を使用して PBX 電話を制御できる機能でした。 Skype for Business Server では、この機能は [Call Via Work] に置き換えられた機能です。
  
[Call Via Work] を使用すると、PBX 電話ユーザーに対して次の機能が有効にされます。
  
- PBX 電話を介して提供される音声による、クリックして呼び出しのエクスペリエンス。
    
- プレゼンス、ユーザー検索、および IM 統合 。たとえば、IM セッションで 2 人の "仕事から通話" ユーザーが、PBX 電話経由で提供される音声を使用して、セッションにオーディオを追加できます。
    
- IM、アプリケーション共有、およびファイル転送を [Call Via Work] 通話に追加する機能。
    
- 1 回クリックで会議参加機能
    
## <a name="how-it-works"></a>メカニズム

Call Via Work は、PBX システムと Skype for Business Server 展開との間のバック to バック ユーザー エージェント (B2BUA) として Unified Communications Web API (UCWA) を使用します。そのため、Skype for Business Server を PBX システムに接続するためにコンピューターサポートの通信アプリケーション (CSTA) ゲートウェイは必要とされません。 UCWA は、モバイルおよび Web クライアントとの接続を可能にする以前のバージョンの Lync Server で導入されたサービスであり、すべてのフロントエンド サーバーに自動的にインストールされます。
  
### <a name="call-workflow-for-a-call-via-work-call"></a>[Call Via Work] 通話の通話ワークフロー

次の図は、ユーザーが [仕事から通話] を有効にした場合に、Skype for Business Server を使用して通話を行う方法を示しています。
  
![[Call Via Work] 通話中の手順を示します。最初に、発信者がクリックして Skype for Business クライアントで他のユーザーに電話します。UCWA が発信者の電話に着信します。 発信者が電話を取ると、受信者が呼び出されます。](../../media/050e88ed-e18e-40c0-84d5-b17fe40c305a.jpg)
  
1. ユーザーは Skype for Business クライアントでユーザーを選択し、電話アイコンをクリックしてユーザーに電話します。 または、IM 会話中に、ユーザーがクリックして、セッションを受け取っているユーザーに電話します。
    
2. 呼び出しを行ったユーザーの PBX 電話が呼び出しを開始します。 この電話の発信者番号には、通話を行うすべてのユーザーの発信者番号に表示するために設定したグローバル電話番号が表示されます。 このグローバル電話番号は、1 人のユーザーの電話に対応する実際の電話番号ではありません。 代わりに、これが自分の発信通話であり、同時に発生する着信呼び出しではないことをユーザーに知らせる視覚的な信号です。 [Call Via Work] を展開する場合は、これらのユーザーにこのグローバル電話番号とそれが何を意味するのかを教育する必要があります。
    
3. 通話を行ったユーザーは、PBX 電話を使用します。 次に、Skype for Business は呼び出し先への音声呼び出しを開始します。 
    
4. 呼び出し先が応答すると、音声呼び出しが開始されます。 2 人のユーザーが既に IM セッションを継続している場合は、続行できます。
    
### <a name="joining-a-conference-with-call-via-work"></a>[仕事から通話] で電話会議に参加する

[Call Via Work] (仕事から通話) ユーザーは、会議 URL をクリックして、スケジュールされた会議に参加できます。 次に、Skype for  Business は、会議サービスがユーザーの PBX 電話にダイヤルするまで、メッセージへのダイヤルアウトを表示します。 次に、Call Via Work ユーザーが PBX 電話を選択し、会議に参加します。
  
[仕事から通話] ユーザーは、Skype for Business の [今すぐミーティング] オプションを使用して今すぐ会議を作成することもできます。  次に、ユーザーに [ **ダイヤルアウト** ] メッセージが表示され、PBX 電話が呼び出されます。
  
Call Via Work ユーザーは、Skype for Business 内から会議ブリッジ番号に電話をかけ、会議にダイヤルインできます。 会議 PIN が必要な場合、ユーザーは PBX 電話を使用して PIN を入力する必要があります。
  
### <a name="incoming-calls"></a>着信呼び出し

[仕事から通話] が有効になっているユーザーが Skype for Business 通話を受信すると、PBX 電話とユーザーの Skype for Business クライアントはすべて同時に呼び出されます (ユーザーが同時呼び出しを設定している場合)。 ユーザーは、PBX 電話を受け取る、または Skype for Business 通知の **[** 承諾] をクリックして、通話を承諾できます。 ユーザーが Skype for Business を使用して通話を承諾した場合、通話の Skype for Business ウィンドウは開いたままです。 ただし、ユーザーが PBX 電話を受け取って通話を受け入れる場合は、Skype for Business 通知ウィンドウが閉じ、Skype for Business セッションは表示されません。PBX 電話を経由する音声通話のみです。
  
[Call Via Work] が有効なユーザーが PBX 呼び出しを受信すると、PBX 電話だけが呼び出されます。
  
## <a name="limitations-of-call-via-work"></a>[仕事から通話] の制限事項

Call Via Work は、ハードウェアのセットアップをほとんど必要としませんが、フル エンタープライズ VoIP またはリモート通話コントロールで使用できる機能に比べて制限がある音声ソリューションです。 [Call Via Work] (仕事から通話) には、次の制限があります。
  
- [Call Via Work] ユーザーが [Call Via Work] コールバック番号への呼び出し転送を設定し、ユーザーがユーザーの電話番号でこのユーザーを会議に招待しようとすると、招待はそのユーザーに届かない。 電話番号ではなく名前をクリックして会議に参加者を招待するユーザーを教育する必要があります。 
    
- 拡張 911 機能と悪意のある呼び出しのトレースは、"仕事から通話" の呼び出し時には使用できません。
    
- [会社から通話] が有効なユーザーは、委任、チーム通話、または応答グループの機能を使用できません。
    
- ユーザーが Skype for Business を使用して会議を録音したり、通話をミュートまたはミュート解除したり、通話を保留または転送したり、コール パークを使用したりすることはできません。
    
- ユーザーは[Call Via Work]を使用して PBX ボイスメール メッセージにアクセスすることはできません。
    
- [仕事から通話] のユーザーは、音声通話として開始されたセッションを、ビデオ、Powerpoint、ホワイトボード、One Note などの通信を含む共同作業会議にエスカレートすることはできません。
    
- [仕事から通話] のユーザーは、2 人通話にユーザーを追加できません。
    
- 電話のペアリングや VDI プラグインのペアリングはサポートされていません。
    
- ユーザーが PBX 電話を使用して (Skype for Business ウィンドウを使用しない) 通話に応答した場合、通話のログは表示されません。
    
- PBX システムが置換で **REFER をサポートしていない** 場合は、次の動作が発生します。 [Call Via Work] 通話中に、ユーザーが PBX 電話から進行中の通話を転送した場合、通話ウィンドウは Skype for Business ウィンドウから消えません。 ユーザーが通話ウィンドウを閉じると、転送先と転送先の間の通話が終了します。 
    
## <a name="prerequisites-for-call-via-work"></a>[仕事から通話] の前提条件

[仕事から通話] に対してすべてのユーザーを有効にするには、いくつかの前提条件が必要です。 これらの前提条件の詳細、およびユーザーの [通話の実行] を [作業から] に対して有効にする手順については [、「Deploy Call Via Work in Skype for Business Server 2015」](../../deploy/deploy-call-via-work.md)を参照してください。 
  
## <a name="see-also"></a>関連項目

[Skype for Business でのリモート通話コントロールの計画](remote-call-control.md)
  
[Deploy Call Via Work in Skype for Business Server 2015](../../deploy/deploy-call-via-work.md)

