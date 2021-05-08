---
title: 直接ルーティングの国コード
ms.author: crowe
author: CarolynRowe
manager: serdars
audience: ITPro
ms.reviewer: NMuravlyannikov
ms.topic: reference
ms.service: msteams
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
f1.keywords:
- NOCSH
description: 最適なメディア パスを選択できるよう、ダイレクト ルーティングのメディア パス国コードを見つけるには、この記事を参照してください。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 56cdc48b33e048776a43a37864930fc153c47aac
ms.sourcegitcommit: c80af314f1a573f99dd66858301c004ccc5410d6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2021
ms.locfileid: "51648126"
---
# <a name="direct-routing-media-path-country-codes"></a>ダイレクト ルーティング メディア パスの国コード

メディアのルーティング パスを選択する場合、既定では、ダイレクト ルーティングは常にセッション ボーダー コントローラー (SBC) のパブリック IP アドレスに基づいてデータセンターを割り当て、常に SBC データセンターに最も近いパスを選択します。

ただし、場合によっては、既定のメディア パスが最適なメディア パスではない可能性があります。たとえば、米国の範囲のパブリック IP をヨーロッパにある SBC に割り当てることができます。 

-MediaRelayRoutingLocationOverride パラメーターを New-CsOnlinePSTNGateway コマンドレットと Set-CsOnlinePSTNGateway コマンドレットで使用することで、メディア トラフィックの優先リージョンを指定できます。 たとえば、次のコマンドは、優先リージョンがドイツ語を指定します。

Set-CSOnlinePSTNGateway -Identity sbc1.contoso.com –MediaRelayRoutingLocationOverride DE 

Microsoft では、通話ログがメディア パスに対するデータセンターの既定の割り当てが SBC データセンターに最も近いパスを使用していないと明確に示している場合にのみ、このパラメーターの設定をお勧めします。 

> [!NOTE]
> -MediaRelayRoutingLocationOverride - このコマンドは、直接ルーティング シナリオでは使用できません。
 
## <a name="country-code-reference-table"></a>国コードリファレンス テーブル

次の表は、-MediaRelayRoutingLocationOverride パラメーターの国コード値を示しています。

| 国         | コード 
|-----------------|--------------------|
| アフガニスタン     | AF |
| アランド諸島   | AX |
| アルバニア         | AL |
| アルジェリア         | DZ |
| 米領サモア  | AS |
| アンドラ         | AD |
| アンゴラ          | AO |
| アンギラ        | AI |
| 南極      | AQ | 
| アンティグア バーブーダ | AG |
| アルゼンチン       | AR |
| アルメニア         | AM |
| アルバ           | AW |
| オーストラリア       | AU |
| オーストリア         | AT |
| アゼルバイジャン      | AZ |
| バハマ         | BS |
| バーレーン         | BH |
| バングラデシュ      | BD |
| バルバドス        | BB |
| ベラルーシ         | BY |
| ベルギー         | BE |
| ベリーズ          | BZ |
| ベナン           | BJ |
| バミューダ         | BM |
| ブータン          | BT |
| ボリビア         | BO |
| ボネール島         | BQ |
| ボスニア ヘルツェゴビナ | BA |
| ボツワナ        | BW |
| ブーベ島   | BV |
| ブラジル          | BR |
| 英国領インド洋地域 | IO |
| 英領バージン諸島 | VG |
| ブルネイ          | BN |
| ブルガリア        | BG |
| ブルキナファソ    | BF |
| ブルンディ         | BI |
| カーボ ベルデ      | CV |
| カンボジア        | KH |
| カメルーン        | CM |
| カナダ          | CA |
| ケイマン諸島  | KY |
| 中央アフリカ共和国 | CF |
| チャド            | TD |
| チリ           | CL |
| 中国           | CN |
| クリスマス島 | CX |
| コズ (キーリング) 諸島 | CC |
| コロンビア        | CO |
| コモロ         | KM |
| コンゴ           | CG |
| コンゴ共和国 (DRC)     | CD |
| クック諸島    | CK |
| コスタリカ      | CR |
| コート・ディボワール   | CI |
| クロアチア         | 人事 |
| キューバ            | CU |
| キュラソー島         | CW |
| キプロス          | CY |
| チェコ語         | CZ |
| デンマーク         | DK |
| ジブチ        | DJ |
| ドミニカ        | DM |
| ドミニカ共和国 | DO |
| エクアドル         | EC |
| エジプト           | EG |
| エルサルバドル     | SV |
| 赤道ギニア | GQ |
| エリトリア         | ER |
| エストニア         | EE |
| Eswatini        | SZ |
| エチオピア        | ET |
| フォークランド諸島 | FK |
| フェロー諸島   | FO |
| フィジー            | FJ |
| フィンランド         | FI |
| フランス          | FR |
| 仏領ギアナ   | GF |
| 仏領ポリネシア | PF |
| フランス領南方地域 | TF |
| ガボ語           | GA |
| ガンビア          | GM |
| ジョージア         | GE |
| ドイツ         | DE |
| ガーナ           | GH |
| ジブラルタル       | GI |
| ギリシャ          | GR |
| グリーンランド       | GL |
| グレナダ         | GD |
| グアドループ      | GP |
| グアム            | GU |
| グアテマラ       | GT |
| ガーンジー        | GG |
| ギニア          | GN |
| Guinea-Bissau   | GW |
| ガイアナ          | GY |
| ハイチ           | こんにちは |
| 聞こえ島とマドナルド諸島 | HM |
| ホンジュラス        | HN |
| 香港特別行政区   | HK |
| ハンガリー         | HU |
| アイスランド         | IS |
| インド           | IN |
| インドネシア       | ID |
| イラン            | IR |
| イラク            | IQ |
| アイルランド         | IE |
| マン島     | インスタント メッセージ |
| イスラエル          | IL |
| イタリア           | IT |
| ジャマイカ         | JM |
| Jan Mayen       | XJ |
| 日本           | JP |
| ジャージー          | JE |
| ヨルダン          | JO |
| カザフスタン      | KZ |
| ケニア           | KE |
| キリバス        | KI |
| 韓国           | KR |
| コソボ          | XK |
| クウェート          | KW |
| キルギス      | KG |
| ラオス            | LA |
| ラトビア          | LV |
| レバノン         | LB |
| レソト         | LS |
| リベリア         | LR |
| リビア           | LY |
| リヒテンシュタイン   | LI |
| リトアニア       | LT |
| ルクセンブルク      | LU |
| Macao SAR       | MO |
| マダガスカル      | MG |
| マラウイ          | MW |
| マレーシア        | MY |
| モルジブ        | MV |
| マリ            | ML |
| マルタ           | MT |
| マーシャル諸島 | MH |
| マルティニーク      | MQ |
| モーリタニア      | MR |
| モーリシャス       | MU |
| マヨット         | YT |
| メキシコ          | MX |
| ミクロネシア      | FM |
| モルドバ         | MD |
| モナコ          | MC |
| モンゴル        | MN |
| モンテネグロ      | ME |
| モントセラト      | MS |
| モロッコ         | MA |
| モザンビーク      | MZ |
| ミャンマー         | MM |
| ナミビア         | NA |
| ナウル           | NR |
| ネパール           | NP |
| オランダ     | NL |
| ニューカレドニア   | NC |
| ニュージーランド     | NZ |
| ニカラグア       | NI |
| ニジェール           | NE |
| ナイジェリア         | NG |
| Niue            | NU |
| ノーフォーク島  | NF |
| 韓国     | KP |
| 北マケドニア | MK |
| 北マリアナ諸島 | NP |
| ノルウェー          | 違います |
| オマーン            | OM |
| パキスタン        | PK |
| パラオ           | PW |
| パレスチナ自治政府 | PS |
| パナマ          | PA |
| パプアニューギニア | PG |
| パラグアイ        | PY |
| ペルー            | PE |
| フィリピン     | PH |
| ピトケアン諸島 | PN |
| ポーランド          | PL |
| ポルトガル        | PT |
| プエルトリコ     | PR |
| カタール           | QA |
| レユニオン         | RE |
| ルーマニア         | RO |
| ロシア          | RU |
| ルワンダ          | RW |
| サバ島            | XS |
| サン・バルテレンティ | BL |
| セントクリストファー・ネーヴィス | KN |
| セントルシア     | LC |
| サンマルタン    | MF |
| サンピエール島とミクロン島 | PM |
| セントビンセント及びグレナディーン諸島 | VC |
| サモア           | WS |
| サンマリノ      | SM |
| サンパウロ・トメ・プリンシペ | ST |
| サウジアラビア    | SA |
| セネガル         | SN |
| セルビア          | RS |
| Seychelles      | SC |
| シエラレオネ    | SL | 
| シンガポール       | SG |
| シント・ユースタティウス  | XE |
| シント・マールテン    | SX |
| スロバキア        | SK |
| スロベニア        | SL |
| ソロモン諸島 | SB |
| ソマリア         | だから |
| 南アフリカ    | ZA |
| サウスジョージアとサウスサンドウィッチ諸島 | GS |
| 南スーダン     | SS |
| スペイン           | ES |
| スリランカ       | LK |
| セントヘレナ、アセンション、トリスタンダクーニャ | SH |
| スーダン           | SD |
| スリナム        | SR |
| Svalbard        | SJ |
| スウェーデン          | Standard Edition |
| スイス     | CH |
| シリア           | SY |
| 台湾          | TW |
| タジキスタン      | TJ |
| タンザニア        | TZ |
| タイ        | TH |
| Timor-Leste     | TL |
| トーゴ            | TG |
| トケラウ         | TK |
| トンガ           | 宛先 |
| トリニダード・トバゴ | TT |
| チュニジア         | TN |
| トルコ          | TR |
| トルクメニスタン    | TM |
| タークス・カイコス諸島 | TC |
| ツバル          | テレビ |
| 米国離島 | UM |
| 米領バージン諸島 | VI |
| ウガンダ          | UG |
| ウクライナ         | UA |
| アラブ首長国連邦 | AE |
| 英国  | GB |
| 米国   | 米国 |
| ウルグアイ         | UY |
| ウズベキスタン      | UZ |
| バヌアツ         | VU |
| バチカン市国    | VA |
| ベネズエラ       | VE |
| ベトナム         | VN |
| ウォリス・フトゥナ | WF |
| イエメン           | YE |
| ザンビア          | ZM |
| ジンバブエ        | ZW |

