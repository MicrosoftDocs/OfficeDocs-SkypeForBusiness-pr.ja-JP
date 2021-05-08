---
title: サービス品質 (QoS) をクライアントにMicrosoft Teamsする
author: SerdarSoysal
ms.author: serdars
manager: Serdars
ms.topic: article
ms.service: msteams
ms.reviewer: vkorlep, siunies
audience: admin
description: サービス品質 (QoS) を使用して、デスクトップ クライアントのネットワーク トラフィックを最適化Microsoft Teams学習します。
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.custom:
- seo-marvel-mar2020
- seo-marvel-apr2020
ms.openlocfilehash: 263e2d07992bd491259b82856413548fcd9741fd
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51094785"
---
# <a name="implement-quality-of-service-qos-in-microsoft-teams-clients"></a>サービス品質 (QoS) をクライアントにMicrosoft Teamsする

グループ ポリシー内でポリシー ベースのサービス品質 (QoS) を使用して、クライアント内の定義済み DSCP 値のソース ポート範囲Teamsできます。 次の表に示すポート範囲は、ワークロードごとにポリシーを作成する開始点です。

*表 1.推奨される初期ポート範囲*

|メディア トラフィックの種類| クライアントの送信元ポート範囲 |プロトコル|DSCP 値|DSCP クラス|
|:--- |:--- |:--- |:--- |:--- |
|オーディオ| 50,000–50,019|TCP/UDP|46|完全優先転送 (EF)|
|ビデオ| 50,020–50,039|TCP/UDP|34|相対的優先転送 (AF41)|
|アプリケーション/画面共有| 50,040–50,059|TCP/UDP|18|相対的優先転送 (AF21)|
| | | | | |

可能な限り、グループ ポリシー オブジェクト内でポリシー ベースの QoS 設定を構成します。 次の手順は[、Skype for Business Server](/SkypeForBusiness/manage/network-management/qos/configuring-port-ranges-for-your-skype-clients#configure-quality-of-service-policies-for-clients-running-on-windows-10)上のクライアントのポート範囲とサービス品質ポリシーの構成に非常に似ています。このポリシーには、必要ない可能性がある追加の詳細がいくつか含まれます。

ドメインに参加しているコンピューターの QoS オーディオ ポリシーを作成Windows 10、最初にグループ ポリシー管理がインストールされているコンピューターにログオンします。 [グループ ポリシーの管理] を開き ([スタート] をクリックし、[管理ツール] をポイントして、[グループ ポリシー管理] をクリックします)、次の手順を実行します。

1. [グループ ポリシーの管理] で、新しいポリシーを作成するコンテナーを探します。 たとえば、すべてのクライアント コンピューターが **Clients** という名前の OU にある場合、新しいポリシーをクライアント OU に作成する必要があります。

1. 適切なコンテナーを右クリックし、[このドメインに GPO を作成する] をクリックし、 **ここにリンクします**。

1. [新 **しい GPO] ダイアログ** ボックスの [名前] ボックスに新しいグループ ポリシー オブジェクトの名前を入力し **、[OK]** をクリックします。

1. 新しく作成したポリシーを右クリックし、[編集] を **クリックします**。

1. グループ ポリシー管理エディターで、[**コンピューター** の構成] を展開し、[Windows 設定]**を** 展開し、[ポリシー ベース **の QoS]** を右クリックし、[新しいポリシーの作成]**をクリックします**。

1. [ **ポリシー ベースの QoS]** ダイアログ ボックスの開きページで、[名前] ボックスに新しいポリシーの名前を **入力** します。 [SPECIFY **DSCP Value]を選択し** 、値を **46 に設定します**。 [ **送信スロットル レートの指定] は** オフのままにし、[次へ] を **クリックします**。

1. 次のページで、[**この** 実行可能ファイル名を持つアプリケーションのみ] を選択し、[次へ]Teams.exeを入力し、[次へ] を **クリックします**。 この設定は、クライアントからの一致するトラフィックのみを優先順位付けするようにポリシー Teams指示します。

1. 3 番目のページで、[任意の送信元 **IP** アドレス] と [任意の宛先 **IP** アドレス] の両方が選択され、[次へ] をクリック **します**。 これら 2 つの設定により、パケットを送信したコンピューター (IP アドレス) とパケットを受信するコンピューター (IP アドレス) に関係なく、パケットが管理されます。

1. 4 ページの [Select **the protocol this QoS policy applies** to](この QoS ポリシーが適用するプロトコルを選択する)ドロップダウン リストから [TCP] と **[UDP]** を選択します。 TCP (伝送制御プロトコル) と UDP (ユーザー データグラム プロトコル) は、最も一般的に使用される 2 つのネットワーク プロトコルです。

1. [ソース ポート番号 **の指定] という見出しの下で**、[このソース ポートまたは範囲 **から] を選択します**。 付属のテキスト ボックスに、オーディオ転送用に予約されているポート範囲を入力します。 たとえば、オーディオ トラフィック用にポート 50000 からポート 50019 を予約した場合は **、50000:50019** という形式でポート範囲を入力します。 [**完了**] をクリックします。

1. 手順 6 と 10 で適切な値を置き換え、ビデオとアプリケーション/デスクトップ共有のポリシーを作成するには、手順 5 ~ 10 を繰り返します。

作成した新しいポリシーは、クライアント コンピューターでグループ ポリシーが更新されるまで有効にされません。 グループ ポリシーは定期的に独自に更新しますが、次の手順に従って、すぐに更新を強制できます。

1. グループ ポリシーを更新する各コンピューターで、管理者としてコマンド プロンプト (管理者として実行)*を開きます*。

1. コマンド プロンプトで、「」と入力します。

   ```console
   gpupdate /force
   ```

## <a name="verify-dscp-markings-in-the-group-policy-object"></a>グループ ポリシー オブジェクトで DSCP マーキングを確認する

グループ ポリシー オブジェクトの値が設定されたと確認するには、次の手順に従います。

1. 管理者としてコマンド プロンプトを開きます (*管理者として実行)。*

1. コマンド プロンプトで、「」と入力します。

   ```console
   gpresult /R > gp.txt
   ```

   これにより、適用された GPO のレポートが生成され、 という名前のテキスト *ファイルにgp.txt。*

   l という名前の読み取り可能な HTML *gp.htm、* 次のコマンドを入力します。

   ```console
   gpresult /H gp.html
   ```

1. 生成されたファイルで、[適用されたグループポリシー オブジェクト] という見出しを探し、先に作成したグループ ポリシー オブジェクトの名前が適用されたポリシーの一覧に含まれています。

1. レジストリ エディターを開き、

   HKEY \_ LOCAL MACHINE Software \_ \\ \\ Policies Microsoft Windows \\ \\ \\ QoS

   表 2 に記載されているレジストリ エントリの値を確認します。

   *表 2.QoS Windowsレジストリ エントリの値*

   |          名前          |  種類  |    データ     |
   |         :---:          | :---:  |    :---:    |
   |    Application Name    | REG_SZ |  Teams.exe  |
   |       DSCP Value       | REG_SZ |     46      |
   |        Local IP        | REG_SZ |     \*      |
   | Local IP Prefix Length | REG_SZ |     \*      |
   |       Local Port       | REG_SZ | 50000-50019 |
   |        プロトコル        | REG_SZ |     \*      |
   |       Remote IP        | REG_SZ |     \*      |
   |    リモート IP プレフィックス    | REG_SZ |     \*      |
   |      Remote Port       | REG_SZ |     \*      |
   |     Throttle Rate      | REG_SZ |     -1      |
   | | | |

1. 使用しているクライアントの [アプリケーション名] エントリの値が正しいか確認し、[DSCP 値] エントリと [ローカル ポート] エントリの両方にグループ ポリシー オブジェクトの設定が反映されていることを確認します。


## <a name="related-topics"></a>関連トピック

[サービス品質 (QoS) を実装するTeams](QoS-in-Teams.md)