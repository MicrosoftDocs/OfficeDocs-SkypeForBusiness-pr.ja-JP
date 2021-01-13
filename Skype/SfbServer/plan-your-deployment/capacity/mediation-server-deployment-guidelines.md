---
title: Skype for Business Server での仲介サーバーの展開ガイドライン
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
ms.collection: IT_Skype16
ms.assetid: 7cc22b87-18d9-45e6-8402-015abd20f2e5
description: このトピックでは、仲介サーバーの展開の計画ガイドラインについて説明します。
ms.openlocfilehash: 245916286fe5f1590581989b8a09daf637c03aa9
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49800092"
---
# <a name="deployment-guidelines-for-mediation-server-in-skype-for-business-server"></a>Skype for Business Server での仲介サーバーの展開ガイドライン
 
このトピックでは、仲介サーバーの展開の計画ガイドラインについて説明します。
  
## <a name="collocated-or-stand-alone-mediation-server"></a>Collocated or Stand-alone Mediation Server?

仲介サーバーは、既定では、中央サイトのフロント エンド プールの Standard Edition サーバーまたはフロントエンド サーバーに同時に展開されます。 処理できる公衆交換電話網 (PSTN) 通話の数とプールに必要なコンピューターの数は、次の条件によって異なっています。
  
- 仲介サーバー プールが制御するゲートウェイ ピアの数。
    
- これらのゲートウェイを経由する高ボリューム トラフィック期間。
    
- メディアが仲介サーバーをバイパスする通話の割合。
    
計画時には、メディア バイパスをサポートしない PSTN 通話および音声ビデオ会議のメディア処理要件と、サポートが必要なビジー時の通話数に対する信号やり取りを処理するために必要な処理を考慮する必要があります。 CPU が十分ではない場合は、仲介サーバーのスタンドアロン プールを展開する必要があります。 さらに、PSTN ゲートウェイ、IP-PBX、および SBC は、1 つのプール内の仲介サーバーと、1 つ以上のスタンドアロン プール内のスタンドアロン仲介サーバーによって制御されるサブセットに分割する必要があります。
  
仲介サーバーのプールと対話する機能がない PSTN ゲートウェイ、IP-PBX、またはセッション ボーダー コントローラー (SBC) を展開した場合は、単一の仲介サーバーで構成されるスタンドアロン プールに関連付ける必要があります。 PSTN ゲートウェイ、PSTN ゲートウェイ、または SPC IP-PBXs実行する必要があるものには、次のようなものがあります。
  
- プール内の仲介サーバー間でネットワーク層ドメイン ネーム システム (DNS) 負荷分散を実行します (それ以外の場合は、プール内のすべての仲介サーバーにトラフィックを均等にルーティングします)。
    
- プール内の仲介サーバーからのトラフィックを受け入れる。
    
Skype for Business Planning Tool を使用して、仲介サーバーとフロントエンド プールを一緒に展開して負荷を処理できるかどうかを評価できます。 環境がこれらの要件を満たできない場合は、スタンドアロンの仲介サーバー プールを展開する必要があります。
  
## <a name="central-site-and-branch-site-considerations"></a>中央サイトとブランチ サイトに関する考慮事項

 中央サイトの仲介サーバーを使用して、ブランチ サイトの IP-PBX ゲートウェイまたは PSTN ゲートウェイの通話をルーティングできます。 ただし、SIP トランクを展開する場合は、各トランクが終了するサイトに仲介サーバーを展開する必要があります。 中央サイトに仲介サーバーを使用すると、ブランチ サイトの IP-PBX または PSTN ゲートウェイの通話がルーティングされますが、メディア バイパスを使用する必要は生じしませんが、メディア バイパスをお勧めします。 これは、メディア バイパスを有効にできると、メディア パスの待機時間が短くなるので、メディア パスが信号パスに従う必要がならないため、メディアの品質が向上する可能性があります。 メディア バイパスにより、プールの処理負荷も軽減することができます。
  
> [!NOTE]
> メディア バイパスは、すべての PSTN ゲートウェイ、IP-PBX、および SBC と相互運用できるとは言えな。 Microsoft は、認定パートナーと一連の PSTN ゲートウェイと SBC をテストし、Cisco IP-PBX でいくつかのテストを行っています。 メディア バイパスは [、Unified](http://partnersolutions.skypeforbusiness.com/solutionscatalog)Communications Open Interoperability Program に記載されている製品とバージョンでのみサポートされます。Lync Server は、Skype for Business エクスペリエンスをサポートおよび拡張するテスト済みデバイス、インフラストラクチャ、およびツールを参照してください。 
  
ブランチ サイトの復元が必要な場合は、存続可能ブランチ アプライアンスまたはフロントエンド サーバー、仲介サーバー、およびゲートウェイの組み合わせをブランチ サイトに展開する必要があります。 (ブランチ サイトの復元の前提は、プレゼンスと会議がサイトで回復性を持たないという前提です)。音声のブランチ サイトの計画に関するガイダンスについては [、「Plan for エンタープライズ VoIP resiliency in Skype for Business Server 」を参照してください](../enterprise-voice-solution/enterprise-voice-resiliency.md)。
  
IP-PBX とのやり取りでは、IP-PBX が複数の早期ダイアログや RFC 3960 の対話による早期メディア操作を正しくサポートしていない場合、IP-PBX から Lync エンドポイントへの着信呼び出しに対して、最初の数語の案内応答がクリッピングされる可能性があります。 中央サイトの仲介サーバーがブランチ サイトでルートが終了する IP-PBX の通話をルーティングしている場合、信号が完了するのにより長い時間が必要になるため、この動作はさらに深刻になります。 この動作が発生した場合、最初の数語のクリッピングを減らす唯一の方法は、ブランチ サイトに仲介サーバーを展開することです。
  
また、中央サイトに TDM PBX がある場合や、IP-PBX によって PSTN ゲートウェイの必要性がなくならない場合は、仲介サーバーおよび PBX に接続する通話ルートにゲートウェイを展開する必要があります。
  
> [!NOTE]
> スタンドアロンの仲介サーバーのメディア パフォーマンスを向上するには、これらのサーバーのネットワーク アダプターで受信側スケーリング (RSS) を有効にする必要があります。 RSS は、着信パケットがサーバーの複数のプロセッサによって平行して処理されるのを可能にします。 詳細については[、「Windows Server の受信側スケーリングの拡張機能」を参照してください](https://go.microsoft.com/fwlink/p/?LinkId=268731)。 RSS を有効にする方法の詳細については、ネットワーク アダプターのドキュメントを参照してください。 
  

