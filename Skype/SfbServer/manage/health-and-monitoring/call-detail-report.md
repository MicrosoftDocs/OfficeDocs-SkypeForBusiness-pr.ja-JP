---
title: Skype for Business Server の通話詳細レポート
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
ms.assetid: 38862e35-3fec-41b9-a035-0b301942d446
description: '概要: Skype for Business Server で使用される通話詳細レポートについて説明します。'
ms.openlocfilehash: 9b02722c8dd872b5703d6b459c2cd48568e39f94
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49826517"
---
# <a name="call-detail-report-in-skype-for-business-server"></a>Skype for Business Server の通話詳細レポート
 
**概要:** Skype for Business Server で使用される通話詳細レポートについて説明します。
  
通話詳細レポートでは、個々の通話の詳細を確認できます。このレポートには、Skype for Business Server によって収集された、ほぼすべての Quality of Experience 指標と統計情報が含まれます。次のようなレポート セクションに分かれています。
  
- 通話情報 
    
- 発信者デバイスと信号測定値
    
- 呼び出し先デバイスと信号測定値
    
- 発信者クライアント イベント
    
- 呼び出し先クライアント イベント
    
- 音声ストリーム (発信者から呼び出し先)
    
- ビデオ ストリーム (発信者から呼び出し先)
    
- 音声ストリーム (呼び出し先から発信者)
    
- ビデオ ストリーム (呼び出し先から発信者)
    
特定のレポートに表示されるカテゴリと測定値は、セッションの種類と、セッションで使用されたエンドポイントの種類に依存します。たとえば、音声のみの通話では、通話にビデオ ストリームがないことにより、ビデオ ストリームの測定値を報告されません。同様に、呼び出し先統計はないが、発信者統計を示すレポートがあることがあります。これは、一般的には、呼び出し先が SIP 準拠のデバイスを使用していなかったことによります。エンドポイントは通話の終了後に、統計を報告します。しかし、(SIP または SIP 統計を関知しない) 携帯電話は、その種類の情報を報告することはできません。だれかに電話して、その人が携帯電話で応答した場合は、通話が終了したときに、その携帯電話からのレポートは得られません。
  
通話の詳細レポートは、特定の通話でメディアの品質の問題が発生した理由を正確に確認するときに最も役立ちます。
  
## <a name="accessing-the-call-detail-report"></a>通話の詳細レポートを表示する

通話の詳細レポートは、以下の任意のレポートから表示できます。
  
- The [Location Report in Skype for Business Server (location-report.md) (by clicking either the Call volume or the Poor call percentage metric)
    
- The [Media Quality Summary Report in Skype for Business Server (summary.md) (by clicking either the Call volume or Poor call percentage metric)
    
- [Skype for Business Server](comparison.md)のメディア品質比較レポート[(Skype for Business Server](call-list-report-0.md)の通話リスト レポートをクリックし、[詳細] 指標をクリック)。
    
- [Skype for Business Server](server-performance.md)のサーバー パフォーマンス レポート ([通話ボリューム] または [低品質通話のパーセンテージ] 指標をクリック)
    
- [Skype for Business Server の通話リスト](call-list-report-0.md)レポート ([詳細] 指標をクリック)
    
通話詳細レポートから、次のいずれかの指標をクリックすると [、Skype for Business Server](device-report.md) のデバイス レポートにアクセスできます。
  
- キャプチャ デバイス
    
- レンダー デバイス
    
また、音声ビデオ エッジ サーバー測定値をクリックすることによってサーバーメディア品質傾向レポートを表示できます。
  
## <a name="making-the-best-use-of-the-call-detail-report"></a>通話の詳細レポートの活用

通話の詳細レポートには、一般的には、マイクのタイムスタンプの誤差、低 SNR 時間、および近端エコー時間の項目のような、250 以上のさまざまな測定値が含まれます。これらの測定値の詳細が思い出せない場合は、測定値のラベル上にマウス ポインターを置きます。多くの場合は、その測定値を説明するツール ヒントが表示されます。
  
測定基準の特定に問題がある場合は、検索ボックスに測定基準ラベルの一部を入力し、[検索] をクリック **します**。 たとえば、低 SNR 時間メトリックが見当たらない場合は、検索ボックスに SNR と入力し、[検索] をクリック **します**。
  
レポートは通話に関する情報のみを追跡します。 呼び出し自体は記録されません。
  
## <a name="filters"></a>フィルター

なし。通話の詳細レポートにはフィルターを適用できません。
  
## <a name="metrics"></a>指標

次の表に、各通話の通話の詳細レポートで提供される情報を示します。
  
**通話の詳細レポートの指標**

|**名前**|**このアイテムを並べ替えることはできますか?**|**説明**|
|:-----|:-----|:-----|
|[**発信者 PAI**] <br/> |いいえ  <br/> |呼び出しを開始したユーザーの P-Asserted-Identity。P-Asserted-Identity は、信頼されたネットワーク内でユーザーの証明済み ID を送信するのに使用されます。  <br/> |
|[**発信者 URI**] <br/> |いいえ  <br/> |呼び出しを開始したユーザーの SIP アドレス。  <br/> |
|[**発信者エンドポイント**] <br/> |いいえ  <br/> |呼び出しを実行したデバイス。  <br/> |
|[**発信者ユーザー エージェント**] <br/> |いいえ  <br/> |呼び出しを実行したデバイスで使用されるソフトウェア。  <br/> |
|[**通話の開始**] <br/> |いいえ  <br/> |呼び出しが最初に開始された日時。  <br/> |
|[**仲介サーバーのバイパス通話**] <br/> |いいえ  <br/> |呼び出しが仲介サーバーを経由せずに PSTN 音声ゲートウェイまたは適切な IP-PBX に接続されたかどうかを示します。  <br/> |
|[**発信者 OS**] <br/> |いいえ  <br/> |呼び出し元のコンピューターのオペレーティング システム。  <br/> |
|[**発信者 CPU**] <br/> |いいえ  <br/> |呼び出しを開始したユーザーのコンピューターに搭載される CPU。  <br/> |
|[**発信者 CPU コア番号**] <br/> |いいえ  <br/> |呼び出しを開始したユーザーが使用するコンピューターのプロセッサ番号。  <br/> |
|[**発信者 CPU 速度**] <br/> |いいえ  <br/> |呼び出しを開始したユーザーが使用するコンピューターの CPU のクロック速度。  <br/> |
|[**発信者 CPU 仮想化**] <br/> |いいえ  <br/> |呼び出しを開始したユーザーが使用するコンピューターでの仮想化 (仮想化されている場合)。  <br/> |
|[**呼び出し先 PAI**] <br/> |いいえ  <br/> |通話に招待されたユーザーの P-Asserted-Identity。P-Asserted-Identity は、信頼されたネットワーク内でユーザーの証明済み ID を送信するのに使用されます。  <br/> |
|[**呼び出し先 URI**] <br/> |いいえ  <br/> |呼び出し先ユーザーの SIP アドレス。  <br/> |
|[**呼び出し先エンドポイント**] <br/> |いいえ  <br/> |呼び出しを受信したデバイス。  <br/> |
|[**呼び出し先ユーザー エージェント**] <br/> |いいえ  <br/> |呼び出しを受信したデバイスで使用されるソフトウェア。  <br/> |
|**Duration** <br/> |いいえ  <br/> |通話時間。  <br/> |
|[**メディア バイパス警告フラグ**] <br/> |いいえ  <br/> |仲介サーバーがバイパスされたときに発行された警告。  <br/> |
|[**呼び出し先 OS**] <br/> |いいえ  <br/> |呼び出し先ユーザーのコンピューターのオペレーティング システム。  <br/> |
|[**呼び出し先 CPU**] <br/> |いいえ  <br/> |呼び出し先ユーザーのコンピューターに搭載される CPU。  <br/> |
|[**呼び出し先コア番号**] <br/> |いいえ  <br/> |呼び出し先ユーザーが使用するコンピューターのプロセッサ番号。  <br/> |
|[**呼び出し先 CPU 速度**] <br/> |いいえ  <br/> |呼び出し先ユーザーが使用するコンピューターの CPU のクロック速度。  <br/> |
|[**呼び出し先 CPU 仮想化**] <br/> |いいえ  <br/> |呼び出し先ユーザーが使用するコンピューターでの仮想化 (仮想化されている場合)。  <br/> |
   

