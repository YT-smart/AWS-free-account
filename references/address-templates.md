# 地区地址模板

根据用户选择的服务器地区，AI 使用以下模板生成随机但合理的注册地址。

**生成原则：**
- 地址必须格式正确、看起来合理
- 街道号码随机，使用真实存在的街道类型
- 城市、州、邮编必须互相匹配
- 手机号使用用户提供的真实手机号，不随机生成
- Full name 可使用常见名字随机组合

---

## 🇨🇳 China（中国）→ 服务器分配到悉尼（默认选项）

注册地区选 China 时，AWS 会将服务器分配到 ap-southeast-2（悉尼）。

```
Full name:    [随机中文拼音名，如 Wei Zhang]
Phone:        [用户提供的手机号，如 +86 13812345678]
Address:      [随机路名] [随机号]
City:         从列表选择：Beijing, Shanghai, Shenzhen, Guangzhou, Hangzhou
State:        与城市匹配
Postal code:  与城市匹配的6位邮编
```

**示例城市-邮编对照：**

| 城市 | 省/直辖市 | 邮编范围 |
| --- | --- | --- |
| Beijing | Beijing | 100000-100999 |
| Shanghai | Shanghai | 200000-200999 |
| Shenzhen | Guangdong | 518000-518999 |
| Guangzhou | Guangdong | 510000-510999 |
| Hangzhou | Zhejiang | 310000-310999 |

**示例地址：**
```
Full name:    Wei Zhang
Phone:        +86 13812345678（用户提供）
Address:      88 Zhongshan Road
City:         Shanghai
State:        Shanghai
Postal code:  200001
```

---

## 🇺🇸 United States（美国）

```
Full name:    [随机英文名，如 James Wilson]
Phone:        [用户提供的手机号]
Address:      [随机3-5位数字] [随机街道名] [St/Ave/Rd/Blvd]
City:         从列表选择
State:        与城市匹配
Postal code:  与城市匹配的5位邮编
```

**示例城市-州-邮编对照：**

| 城市 | 州 | 邮编范围 |
| --- | --- | --- |
| San Francisco | California (CA) | 94101-94199 |
| Los Angeles | California (CA) | 90001-90099 |
| New York | New York (NY) | 10001-10299 |
| Chicago | Illinois (IL) | 60601-60699 |
| Seattle | Washington (WA) | 98101-98199 |
| Austin | Texas (TX) | 78701-78799 |
| Denver | Colorado (CO) | 80201-80299 |
| Portland | Oregon (OR) | 97201-97299 |

**示例地址：**
```
Full name:    James Wilson
Phone:        +86 13812345678（用户提供）
Address:      4521 Oakwood Ave
City:         San Francisco
State:        California
Postal code:  94132
```

> 注意：即使注册地区选美国，Phone Number 字段填的是用户自己的手机号（含国家区号）。AWS 注册表单的 Phone Number 区号下拉框需要选择对应国家（如 +86），号码部分填用户的手机号。

---

## 🇯🇵 Japan（日本）

```
Full name:    [随机日式罗马名或英文名，如 Takeshi Yamada]
Phone:        [用户提供的手机号]
Address:      [区名]-[丁目]-[番]-[号] 的英文格式
City:         Tokyo, Osaka, Yokohama, Nagoya
State:        与城市匹配的都道府县
Postal code:  3位-4位格式，如 100-0001
```

**示例城市-邮编对照：**

| 城市 | 都道府县 | 邮编范围 |
| --- | --- | --- |
| Tokyo (Chiyoda) | Tokyo | 100-0001 ~ 102-0099 |
| Tokyo (Shibuya) | Tokyo | 150-0001 ~ 150-0099 |
| Osaka (Chuo) | Osaka | 540-0001 ~ 542-0099 |
| Yokohama | Kanagawa | 220-0001 ~ 231-0099 |

**示例地址：**
```
Full name:    Takeshi Yamada
Phone:        +86 13812345678（用户提供）
Address:      2-8-1 Marunouchi
City:         Tokyo
State:        Tokyo
Postal code:  100-0005
```

---

## 生成规则

1. **数字随机化**：门牌号每次随机，不要反复使用同一个地址。
2. **格式正确**：邮编位数必须与该国家标准一致。
3. **城市-州-邮编匹配**：三者必须属于同一地区。
4. **街道名自然**：使用常见的街道名和后缀，避免编造离奇名称。
5. **手机号用用户的**：Phone Number 一律填用户提供的真实手机号，只是区号下拉框按实际选择。
