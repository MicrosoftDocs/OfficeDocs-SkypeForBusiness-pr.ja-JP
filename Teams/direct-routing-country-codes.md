---
title: 国コードを直接ルーティングする
ms.author: crowe
author: CarolynRowe
manager: serdars
audience: ITPro
ms.reviewer: NMuravlyannikov
ms.topic: reference
ms.service: msteams
localization_priority: Normal
search.appverid: MET150
ms.collection: Teams_ITAdmin_Help
appliesto:
- Microsoft Teams
description: この記事では、ダイレクトルーティング用のメディアパスの国コードについて説明します。
ms.openlocfilehash: 5956f538df5aefc356e960f8eb2817602ef99884
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/07/2019
ms.locfileid: "36237459"
---
# <a name="direct-routing-media-path-country-codes"></a>ダイレクトルーティングメディアパスの国コード

メディアのルーティングパスを選ぶ際には、既定では、セッション境界コントローラー (SBC) のパブリック IP アドレスに基づいて、常にデータセンターが割り当てられ、SBC データセンターに最も近いパスが選択されます。

ただし、場合によっては、既定のメディアパスが最適なメディアパスでない可能性があります。たとえば、米国の範囲からのパブリック IP は、ヨーロッパの SBC に割り当てられている場合があります。 

-MediaRelayRoutingLocationOverride パラメーターと共に CsOnlinePSTNGateway と CsOnlinePSTNGateway コマンドレットを使用することで、メディアトラフィックの優先領域を指定できます。 たとえば、次のコマンドは、優先領域がドイツであることを示します。

Set-CSOnlinePSTNGateway-Identity sbc1.contoso.com – MediaRelayRoutingLocationOverride DE 

このパラメーターを設定することは、メディアパスに対するデータセンターの既定の割り当てでは、SBC データセンターに最も近いパスを使わないことを明示的に示していることに注意してください。 
 
## <a name="country-code-reference-table"></a>国コード参照テーブル

次の表では、-MediaRelayRoutingLocationOverride パラメーターの国コード値を示します。

| 居住         | プログラム 
|-----------------|--------------------|
| アフガニスタン     | AF |
| オーランド諸島   | AX4 |
| アルバニア         | AL |
| アルジェリア         | DZ |
| アメリカ領サモア  | も |
| アンドラ         | AD |
| アンゴラ          | AO |
| アンギラ        | AL |
| 南極      | AQ | 
| アンティグア バーブーダ | AG |
| アルゼンチン       | AR |
| アルメニア         | 私 |
| アルバ           | AW |
| オーストラリア       | AU |
| オーストリア         | 自宅 |
| アゼルバイジャン      | AZ |
| バハマ         | BS |
| バーレーン         | BH |
| バングラデシュ      | BD |
| バルバドス        | BB |
| ベラルーシ         | BY |
| ベルギー         | ば |
| ベリーズ          | BZ |
| ベナン           | BJ |
| バーミューダー諸島         | BM |
| ブータン          | BT |
| ボリビア         | BO |
| ボネール         | BQ |
| ボスニア・ヘルツェゴビナ | BA |
| ボツワナ        | BW |
| ブーベ島   | BV |
| ブラジル          | BR |
| 英領インド洋地域 | IRQ |
| 英領バージン諸島 | VG |
| ブルネイ          | BN |
| ブルガリア        | BG |
| ブルキナ ファソ    | BF |
| ブルンジ         | 両 |
| カーボベルデ      | [CV] |
| カンボジア        | HTTPS://C2RSETUP.OFFICEAPPS.LIVE.COM/C2R/DOWNLOAD.ASPX?PRODUCTRELEASEID=LANGUAGEPACK&LANGUAGE=KM-KH&PLATFORM=X64&SOURCE=O16LAP&VERSION=O16GA |
| カメルーン        | ILM-CM |
| カナダ          | FR-CA |
| Cayman Islands  | アヒル |
| 中央アフリカ共和国 | 接続料金 |
| チャド            | 来 |
| チリ           | CL |
| 中国           | CN |
| クリスマス島 | CX |
| ココス諸島 | 送付 |
| コロンビア        | CO |
| コモロ         | KM |
| 民主           | 重心 |
| コンゴ民主共和国     | 再生 |
| クック諸島    | 皿 |
| コスタリカ      | 改行 |
| コートジボワール   | 項目 |
| クロアチア         | 人事 |
| キューバ            | CU |
| キュラソー島 (         | 貫 |
| キプロス          | CY |
| Czechia         | CZ |
| デンマーク         | DK |
| ジブチ        | DJ |
| ドミニカ        | ダイレクト |
| Dominican Republic (República Dominicana) | 作業 |
| エクアドル         | EC |
| エジプト           | EG |
| El Salvador     | SV |
| 赤道ギニア | GQ |
| エリトリア         | ユーザ |
| エストニア         | EE |
| Eswatini        | SZ |
| エチオピア        | サーブ |
| フォークランド諸島 | FK |
| Faroe Islands   | ライブラリの |
| フィジー            | FJ |
| フィンランド         | FI |
| フランス          | FR |
| フランス領ギアナ   | GF |
| 仏領ポリネシア | いい |
| フランス領南極地方 | TF |
| ガボン           | GA |
| ガンビア          | 利益 |
| ジョージア         | GE |
| ドイツ         | DE |
| ガーナ           | GH |
| ジブラルタル       | GI |
| ギリシャ          | GR |
| グリーンランド       | OPENGL |
| グレナダ         | GD-GB&PLATFORM |
| グアドループ      | GP |
| グアム            | GU-IN&PLATFORM |
| グアテマラ       | GT GROUP |
| ガーンジー島        | ブログ |
| ギニア          | おける |
| ギニア   | GW |
| ガイアナ          | GY |
| ハイチ           | こんにちは |
| [聞こえる島とマクドナルド諸島] | HM |
| ホンジュラス        | HN |
| 香港特別自治区   | HK |
| ハンガリー         | HU |
| アイスランド         | い |
| インド           | チェックイン |
| インドネシア       | ID |
| イラン            | 赤外線 |
| イラク            | IQ |
| アイルランド         | IE |
| マン島     | インスタント メッセージ |
| イスラエル          | IL |
| イタリア           | て |
| ジャマイカ         | JM |
| ヤンマイエンヤンマイエン       | XJ |
| 日本           | JP |
| 島          | JE |
| ヨルダン          | JO |
| カザフスタン      | HTTPS://C2RSETUP.OFFICEAPPS.LIVE.COM/C2R/DOWNLOAD.ASPX?PRODUCTRELEASEID=LANGUAGEPACK&LANGUAGE=KK-KZ&PLATFORM=X64&SOURCE=O16LAP&VERSION=O16GA |
| ケニア           | KE |
| キリバス        | KI |
| 韓国           | KR |
| ・・ Vo          | XK |
| クウェート          | ワーカ |
| キルギスタン      | KG |
| ラオス            | 中南米 |
| ラトビア          | LV |
| レバノン         | 1000 |
| レソト         | 通話 |
| リベリア         | LR |
| リビア           | 強制的 |
| リヒテンシュタイン   | リスト |
| リトアニア       | 会社 |
| ルクセンブルク      | LU |
| マカオ       | 月 |
| マダガスカル      | MG |
| マラウイ          | さん |
| マレーシア        | MY |
| モルジブ        | MIRRORVIEW |
| マリ            | ML |
| マルタ           | スレッド |
| マーシャル諸島 | MH |
| マルチニーク      | TRIGGERS |
| モーリタニア      | クーパー |
| モーリシャス       | MU |
| マヨット島         | YT |
| メキシコ          | MX |
| ミクロネシア      | FM |
| モルドバ         | MD |
| モナコ          | MC |
| モンゴル        | MN |
| モンテネグロ      | 自分 |
| モントセラト      | VERDANA |
| モロッコ         | 100 |
| モザンビーク      | MZ |
| ビルマ         | TU |
| ナミビア         | NA |
| ナウル           | NR |
| ネパール           | 受信 |
| オランダ     | NL |
| ニューカレドニア   | INSIDE |
| ニュージーランド     | ニュージーランド |
| ニカラグア       | SYSTEM.NI.DLL |
| ニジェール           | ケース |
| ナイジェリア         | プロファイリング |
| ニウエ            | ニュー |
| ノーフォーク島  | ユーティリティー |
| 北朝鮮     | KP |
| 北マケドニア | MK-MK&PLATFORM |
| 北マリアナ諸島 | 受信 |
| ノルウェー          | 違います |
| オマーン            | 原則 |
| パキスタン        | 主 |
| パラオ           | PW |
| Palestinian Authority | .PS |
| パナマ          | PA |
| パプアニューギニア | PG |
| パラグアイ        | PY |
| ペルー            | PE |
| フィリピン     | PH |
| ピトケアン島 | 量 |
| ポーランド          | PL |
| ポルトガル        | PT |
| プエルトリコ     | 広報 |
| カタール           | QA |
| レユニオン         | リエンジニアリング |
| ルーマニア         | RO |
| ロシア          | ル |
| ルワンダ          | RW |
| サバ島            | DMX |
| サン Barthelemy | BL |
| Saint Kitts and Nevis | KN |
| セントルシア     | LC |
| サン Martin    | メイン |
| サンピエール・ミクロン | PM |
| セントビンセントおよびグレナディーン諸島 | VC-1 |
| サモア           | WS-METADATA |
| サンマリノ      | MANAGER |
| サンサントメとプリンシペ | 短期 |
| サウジアラビア    | SA |
| セネガル         | SN |
| セルビア          | RS |
| セーシェル      | SC |
| シエラレオネ    | SL | 
| シンガポール       | SG |
| シント・ユースタティウス島  | XE |
| シントマルタン島    | SX |
| スロバキア        | SK |
| スロベニア        | SL |
| ソロモン諸島 | SB |
| ソマリア         | だから |
| 南アフリカ    | TN-ZA |
| サウスジョージア・サウスサンドウィッチ諸島 | GS |
| 南スーダン     | 変動 |
| スペイン           | 可 |
| Sri Lanka       | HTTPS://C2RSETUP.OFFICEAPPS.LIVE.COM/C2R/DOWNLOAD.ASPX?PRODUCTRELEASEID=LANGUAGEPACK&LANGUAGE=SI-LK&PLATFORM=X64&SOURCE=O16LAP&VERSION=O16GA |
| セントヘレナ、アセンション、トリスタンダクーニャ | 悪夢 |
| スーダン           | SD |
| スリナム        | SR |
| 諸島        | SJ |
| スウェーデン          | SE |
| スイス     | チャンネル |
| シリア           | SY |
| 台湾          | MS |
| タジキスタン      | TJ |
| タンザニア        | ロシア |
| タイ        | パー |
| ティモール・ティモール     | TL |
| トーゴ            | TG |
| トケラウ         | TK |
| トンガ           | 宛先 |
| トリニダード・トバゴ | 必ず |
| チュニジア         | TN |
| トルコ          | TR |
| トルクメニスタン    | TM |
| タークス・カイコス諸島 | TC |
| ツバル          | チューナー |
| 米領諸島 | UM |
| 米領バージン諸島 | 第 |
| ウガンダ          | UG-CN&PLATFORM |
| ウクライナ         | ウクライナ |
| アラブ首長国連邦 | AE |
| 英国  | 以上 |
| 米国   | プロセッサー |
| ウルグアイ         | UY |
| ウズベキスタン      | UZ |
| バヌアツ         | VU |
| バチカンの市区町村    | VA |
| ベネズエラ       | わかり |
| ベトナム         | HTTPS://C2RSETUP.OFFICEAPPS.LIVE.COM/C2R/DOWNLOAD.ASPX?PRODUCTRELEASEID=LANGUAGEPACK&LANGUAGE=VI-VN&PLATFORM=X64&SOURCE=O16LAP&VERSION=O16GA |
| ワリス・フテュナ諸島 | ワークフロー |
| イエメン           | すぎる |
| ザンビア          | ZM |
| ジンバブエ        | ZW |

