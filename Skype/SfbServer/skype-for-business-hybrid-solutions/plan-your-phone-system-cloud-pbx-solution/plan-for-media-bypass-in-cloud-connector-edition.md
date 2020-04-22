---
title: Cloud Connector エディションでメディアバイパスを計画する
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 11/15/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: e69ac58c-e8fe-40bc-a4c8-f0a0190fbaa7
description: このトピックでは、Cloud Connector エディションバージョン2.0 以降でメディアバイパスを実装する場合の計画の検討事項について説明します。 メディアバイパスの展開の詳細については、「Cloud Connector エディションでメディアバイパスを展開する」を参照してください。
ms.openlocfilehash: f9da5df4815c731b479f5d2333f26546be0daf4c
ms.sourcegitcommit: ea54990240fcdde1fb061489468aadd02fb4afc7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/22/2020
ms.locfileid: "43778783"
---
# <a name="plan-for-media-bypass-in-cloud-connector-edition"></a>Cloud Connector エディションでメディアバイパスを計画する
 
このトピックでは、Cloud Connector エディションバージョン2.0 以降でメディアバイパスを実装する場合の計画の検討事項について説明します。 メディアバイパスの展開の詳細については、「 [Cloud Connector エディションでメディアバイパスを展開](deploy-media-bypass-in-cloud-connector.md)する」を参照してください。
  
メディアバイパスを使用すると、クライアントはメディアを公衆交換電話網 (PSTN) の次ホップに直接送信できます。ゲートウェイまたはセッションボーダーコントローラー (SBC) を使用して、Cloud Connector Edition コンポーネントをメディアパスから削除します。
  
メディアバイパスは、待機時間、パケット損失の可能性、および潜在的な障害点の数を減らすことで、音声品質を向上させることができます。 バイパスされた通話のメディア処理を排除することで、クラウドコネクタの負荷が軽減されます。これにより、同時呼び出しの数が増加し、スケーラビリティが向上します。 
  
 クラウドコネクタをメディア処理タスクから解放すると、インフラストラクチャに必要な Cloud Connector アプライアンスの数が減少する可能性があるため、可能な場合は常にメディアバイパスを有効にする必要があります。
  
## <a name="how-media-bypass-affects-media-and-signaling-pathways"></a>メディアバイパスがメディアと信号経路に与える影響

信号はメディアバイパスの有無にかかわらず同じパスになりますが、メディアの流れは異なります。 次の図は、メディアバイパスを使用する場合と使用しない場合のトポロジでのメディアと信号経路を示しています。 
  
たとえば、メディアバイパスを使用しない次のトポロジでは、Skype for Business クライアントは PSTN 通話を外部番号に発信し、SIP シグナリングは Office 365 に送られ、Office 365 はエンドユーザーの音声ポリシーに従ってシグナリングトラフィックを転送します。 Cloud Connector ユーザーの場合、音声ポリシーは、シグナリングトラフィックを Cloud Connector エッジサーバーにリダイレクトします。これにより、シグナリングトラフィックは、Cloud Connector 仲介サーバーを介して PSTN セッションボーダーコントローラー (SBC) またはゲートウェイにルーティングされます。 メディアは、次の図に示すように、Skype for Business クライアントから Cloud Connector 仲介サーバー、次に SBC またはゲートウェイに流れます。
  
**メディアバイパスを使用しないメディアおよび信号経路**

![メディアバイパスを使用しない信号](../../media/5cd7e3bf-2565-4bd9-ad5a-f03e13c01060.png)
  
PSTN からの着信通話では、逆方向の同じ信号パスが使用されます。 内部ユーザーの場合、メディアは引き続き、Skype for Business クライアントと Cloud Connector 仲介サーバー、次に SBC またはゲートウェイの間でフローします。
  
次のトポロジでは、メディアバイパスが使用されますが、次の図に示すように、media は Skype for Business クライアントと SBC またはゲートウェイの間で直接転送されます。
  
**メディアバイパスを使用したメディアと信号の経路**

![メディアバイパスを使用した信号](../../media/60400c38-4921-4964-89f2-5e53b68fb497.png)
  
## <a name="multi-site-scenario-and-media-bypass"></a>マルチサイトのシナリオおよびメディアバイパス

メディアバイパスは、単一の Cloud Connector アプライアンスを使用して、複数のサイトにテレフォニーサービスを提供する場合にも役立ちます。 Cloud Connector は発信元または宛先番号に基づいて通話をルーティングできないため、ほとんどの企業では、ルーティングを決定するために、クラウドコネクタの背後に SBC またはゲートウェイを展開しています。 メディアバイパスこのシナリオでは、次の図に示すように、クライアントと中央の SBC またはゲートウェイ間のホップを削除します。
  
**マルチサイトアプリケーション**

![Cloud Connector のマルチサイトの例](../../media/ace8dc3c-1082-46a2-b8b4-98cbf678620e.png)
  
1. SIP トラフィックは、Zurich フルタ内のユーザーから Office 365 に送られます。
    
2. 次に、ユーザーの音声ルーティングポリシーで指定されているように、アムステルダムの Cloud Connector アプライアンスにトラフィックがルーティングされます。
    
3. アムステルダムの Cloud Connector アプライアンスは、アムステルダムにある中央ゲートウェイに SIP トラフィックを送信します。
    
4. アムステルダムにある中央ゲートウェイは、適切なルーティング決定を行い、そのトラフィックを Zurich フルタの SBC またはゲートウェイに送信します。メディアは、「Skype for Business クライアントと、アムステルダムの SBC またはゲートウェイの間で直接フローします。
    
   このアプローチを使用すると、cloud connector が集中管理されているクラウドコネクタ展開1つにつき、より多くのユーザーが提供されます。 クラウドコネクタがメディアパスから除外されている場合でも、集中化された複数サイトシナリオでは、集中型 SBC またはゲートウェイを通過するために必要とされるように、WAN を2回通過する可能性があります。
  
クライアントが企業ネットワークの外部に発信呼び出しを行う場合、メディアトラフィックは、次の図に示すように、Cloud Connector のエッジサーバーと仲介サーバー、および Zurich フルタとアムステルダム間の WAN リンクを経由してフローします。
  
![Cloud Connector のマルチサイトの例2](../../media/ef95839c-4552-440e-9698-7615707a1b50.png)
  
## <a name="supported-clients-for-media-bypass"></a>メディアバイパスに対してサポートされているクライアント

メディアバイパスの最初のリリースでは、サポートされている唯一のクライアントは、Microsoft 365 Apps for enterprise、version 16.0.7870.2020 以上の一部である Skype for Business 2016 Windows クライアントです。 お客様は、現在、延期、または最初のリリース延期を使用して、任意のチャネルを使用できます。 
  
> [!NOTE]
> クライアントの VPN ソリューションを Skype for Business クライアントと組み合わせて使用している場合、メディアバイパスは VPN 分割トンネル構成でのみサポートされます。 
  
リリースチャネルの詳細については、「 [Microsoft 365 Apps for enterprise の更新プログラムチャネルの概要](https://support.office.com/article/Overview-of-update-channels-for-Office-365-ProPlus-9ccf0f13-28ff-4975-9bd2-7e4ea2fefef4?ui=en-US&amp;rs=en-US&amp;ad=US)」を参照してください。
  
さまざまなチャネルの最新リリースバージョンのクライアントについては、「 [Microsoft 365 Apps for enterprise の更新プログラムのリリース情報](https://docs.microsoft.com/officeupdates/release-notes-office365-proplus)」を参照してください。 
  
## <a name="cloud-connector-capacity-considerations-with-media-bypass"></a>メディアバイパスに関する Cloud Connector の容量に関する考慮事項

メディアバイパスを使用せず、ハードウェアに応じて、Cloud Connector アプライアンスは、仲介サーバーを経由してメディアを通過する必要がある50から500の同時通話を処理できます。 詳細については、「 [Plan For Skype for Business Cloud Connector Edition](https://technet.microsoft.com/library/mt605227.aspx)」を参照してください。 
  
メディアバイパスが有効になっている場合、サポートされているバージョンの内部クライアントが仲介サーバーを使用しないため、内部クライアントの数が大幅に増加する可能性があります。 
  
前述したように、外部クライアントまたはサポートされていないクライアントは、メディア用の Cloud Connector エッジと仲介サーバーを使用します。 サイトに配置する必要がある Cloud Connector アプライアンスの数を計算する場合は、サポートされていないクライアントの外部ユーザーとユーザーからのトラフィックを考慮する必要があります。
  
## <a name="cloud-connector-supports-always-bypass-mode"></a>Cloud Connector は常にバイパスモードをサポートする

Cloud Connector は常にバイパスモードのみをサポートします。 オンプレミスの環境では、2つのオプションがあります。常にバイパスして、サイトと地域の情報を使用します。
  
常にバイパスとは、内部クライアントと送信元または送信先のすべての PSTN 通話に対してメディアバイパスが試行されることを意味します。 クライアントが内部か外部かを判断するには、仲介サーバーの仮想マシン上の web サイトが使用されます。 クライアントがサイトに到達できる場合は、[内部] として認識され、メディアバイパスが使用されます。 クライアントがサイトに到達できない場合 (たとえば、クライアントがホームネットワーク上にある場合)、メディアバイパスは使用されません。 
  
常にバイパスする必要があるのは、PSTN サイト内のユーザーと PSTN ゲートウェイ間の接続に障害がある場合です。 
  
詳細については、「 [Plan For Skype for Business Cloud Connector Edition](https://technet.microsoft.com/library/mt605227.aspx)」を参照してください。 
  
たとえば、次の図では、ヨーロッパユーザーがアムステルダムの3つのセッションボーダーコントローラー (sbc) に適切に接続されている必要がありますが、US 西部ユーザーはシアトルの2つの SBCs に十分に接続されている必要があります。 適切に接続されているということは、それらが SBCs またはゲートウェイと同じネットワークサイトにあるか、または適切な帯域幅を持つ WAN リンクに配置されることを意味します。
  
![Cloud Connector の容量](../../media/efb2269b-d44f-474e-aea8-c5158e729cfe.png)
  
> [!NOTE]
> Zurich フルタのユーザーがシアトルのオフィスに移動し、内部ネットワークを使用して、(インターネットを経由するのではなく) ヨーロッパの移動元のユーザーとゲートウェイ間のメディアトラフィックを配信する場合は、ヨーロッパの言語やゲートウェイが配置されているシアトルのオフィスとアムステルダムのオフィスの接続が良好であることを確認する必要があります。 
  
## <a name="codecs-used-in-media-bypass"></a>メディアバイパスで使用されるコーデック

メディアバイパスが有効になっている場合、クライアントと SBC またはゲートウェイ間のメディアトラフィックでは、A-g-dl-p コーデックが使用されます。 
  
## <a name="see-also"></a>関連項目

[Cloud Connector エディションでのメディアバイパスの展開](deploy-media-bypass-in-cloud-connector.md)
