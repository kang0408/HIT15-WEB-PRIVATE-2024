# HIT15-WEB-PRIVATE-2024 - WEEK 13

---

#### [Home](../README.html)

---

#### [I. String methods](#i-string-methods)

#### [II. Array](#ii-array)

#### [III. Object](#iii-object)

---

#### I. String methods

**1. slice()**

- Trích xuất một phần của chuỗi dựa trên chỉ số bắt đầu và kết thúc (không bao gồm chỉ số kết thúc)
- Không làm thay đổi chuỗi góc và trả về một chuỗi mới
- **Cú pháp:**

  ```js
  str.slice(startIndex, endIndex);
  ```

  - `startIndex`: Vị trí bắt đầu (bắt buộc).
  - `endIndex`: Vị trí kết thúc (không bắt buộc). Nếu không được cung cấp, phương thức lấy từ `startIndex` đến hết chuỗi.
  - Hỗ trợ chỉ số âm, tính từ cuối chuỗi.

- **Ví dụ:**

  ```js
  const text = "JavaScript is fun";
  console.log(text.slice(0, 10)); // "JavaScript"
  console.log(text.slice(11)); // "is fun"
  console.log(text.slice(-3)); // "fun" (chỉ số âm tính từ cuối chuỗi)
  ```

**2. substring()**

- Trích xuất một phần của chuỗi giữa hai chỉ số.
- Không bao gồm ký tự tại chỉ số kết thúc.
- Không hỗ trợ chỉ số âm.

- **Cú pháp:**

  ```js
  str.substring(startIndex, endIndex);
  ```

  - `startIndex`: Vị trí bắt đầu (bắt buộc).
  - `endIndex`: Vị trí kết thúc (không bắt buộc). Nếu không được cung cấp, lấy từ `startIndex` đến hết chuỗi.
  - Không hỗ trợ chỉ số âm.

- **Ví dụ:**
  ```js
  const text = "JavaScript";
  console.log(text.substring(0, 4)); // "Java"
  console.log(text.substring(4)); // "Script"
  console.log(text.substring(4, 0)); // "Java" (hoán đổi tham số)
  console.log(text.substring(-4, 4)); // "Java" (chỉ số âm được coi là 0)
  ```

**3. trim()**

- Loại bỏ khoảng trắng ở đầu và cuối chuỗi
- Không thay đổi chuỗi gốc và trả về chuối mới
- **Cú pháp:**

  ```js
  str.trim();
  ```

- **Ví dụ:**

  ```js
  const text = "   Hello World!   ";
  console.log(text.trim()); // "Hello World!"
  ```

**4. includes()**

- Kiểm tra xem chuỗi có chứa một chuỗi con cụ thể hay không
- Phân biệt chữ hoa và chữ thường
- Trả về `true` nếu tìm thấy, ngược lại trả về `false`
- **Cú pháp:**

  ```js
  str.includes(substring, startIndex);
  ```

  - `searchString`: Chuỗi cần kiểm tra (bắt buộc).
  - `position`: Vị trí bắt đầu tìm kiếm (không bắt buộc, mặc định là 0).

- **Ví dụ:**

  ```js
  const text = "JavaScript is awesome";
  console.log(text.includes("Java")); // true
  console.log(text.includes("script")); // false (phân biệt chữ hoa/chữ thường)
  console.log(text.includes("Java", 5)); // false (bắt đầu tìm từ chỉ số 5)
  ```

**4. split()**

- Chia chuỗi thành mảng các chuỗi nhỏ dựa trên một ký tự hoặc chuỗi con dùng làm điểm phân tách.

- Nếu không có `separator`, kết quả sẽ là mảng chứa toàn bộ chuỗi gốc.

- **Cú pháp:**

  ```js
  str.split(separator, limit);
  ```

  - `separator`: Ký tự hoặc chuỗi làm ranh giới (bắt buộc).
  - `limit`: Số phần tử tối đa trong mảng kết quả (không bắt buộc).

- **Ví dụ:**

  ```js
  const text = "apple,banana,cherry";
  console.log(text.split(",")); // ["apple", "banana", "cherry"]
  console.log(text.split(",", 2)); // ["apple", "banana"]
  console.log(text.split("")); // ["a", "p", "p", "l", "e"]
  ```

**5. indexOf()**

- Trả về chỉ số của lần xuất hiện đầu tiên của một chuỗi con.
- Phân biệt chữ hoa và chữ thường.
- Nếu không tìm thấy, trả về -1.
- **Cú pháp:**

  ```js
  str.indexOf(searchValue, startIndex);
  ```

  - `searchValue`: Chuỗi con cần tìm (bắt buộc).
  - `start`: Vị trí bắt đầu tìm kiếm (không bắt buộc, mặc định là 0).

- **Ví dụ:**

  ```js
  const text = "JavaScript is awesome";
  console.log(text.indexOf("Script")); // 4
  console.log(text.indexOf("is")); // 11
  console.log(text.indexOf("Java", 5)); // -1 (bắt đầu tìm từ chỉ số 5)
  ```

- **Ví dụ:**

```js
const text = "JavaScript";
console.log(text.substring(0, 4)); // "Java"
console.log(text.substring(4)); // "Script"
console.log(text.substring(4, 0)); // "Java" (tự động đổi thứ tự nếu start > end)
```

**7. replace()**

- Thay thế chuỗi con đầu tiên tìm thấy bằng một chuỗi khác.
- Không thay đổi chuỗi gốc, trả về chuỗi mới.
- **Cú pháp:**

  ```js
  str.replace(searchValue, replaceValue);
  ```

  - `searchValue`: Chuỗi hoặc biểu thức cần thay thế (bắt buộc).
  - `replaceValue`: Chuỗi thay thế (bắt buộc).

- **Ví dụ:**

  ```js
  const text = "I love JavaScript";
  console.log(text.replace("JavaScript", "Python")); // "I love Python"
  console.log(text.replace("love", "like")); // "I like JavaScript"
  ```

**8. charAt()**

- Trả về ký tự tại vị trí chỉ định trong chuỗi.
- **Cú pháp:**

  ```js
  str.charAt(index);
  ```

- **Ví dụ:**

  ```js
  const text = "JavaScript";
  console.log(text.charAt(0)); // "J"
  console.log(text.charAt(4)); // "S"
  console.log(text.charAt(10)); // "" (không tồn tại)
  ```

**9. Bảng mô tả các phương thức chuỗi**

| **Phương thức** | **Mục đích**                                                     | **Đặc điểm**                                                                                    | **Kết quả trả về**                      |
| --------------- | ---------------------------------------------------------------- | ----------------------------------------------------------------------------------------------- | --------------------------------------- |
| `slice()`       | Trích xuất một phần chuỗi dựa trên chỉ số bắt đầu và kết thúc.   | Không thay đổi chuỗi ban đầu, hỗ trợ chỉ số âm, không bao gồm chỉ số kết thúc.                  | Chuỗi con mới.                          |
| `substring()`   | Trích xuất một phần chuỗi dựa trên chỉ số bắt đầu và kết thúc.   | Không hỗ trợ chỉ số âm, nếu `startIndex` > `endIndex` thì tự động hoán đổi.                     | Chuỗi con mới.                          |
| `trim()`        | Loại bỏ khoảng trắng ở đầu và cuối chuỗi.                        | Không thay đổi chuỗi ban đầu, không có tham số.                                                 | Chuỗi mới không có khoảng trắng.        |
| `includes()`    | Kiểm tra xem chuỗi có chứa một chuỗi con cụ thể không.           | Phân biệt chữ hoa và chữ thường, hỗ trợ tham số `position` để chỉ định vị trí bắt đầu tìm kiếm. | `true` nếu tìm thấy, ngược lại `false`. |
| `split()`       | Chia chuỗi thành một mảng dựa trên ký tự                         | Không làm thay đổi chuỗi ban đầu, có thể giới hạn số phần tử trong mảng bằng tham số `limit`.   | Một mảng các chuỗi con.                 |
| `indexOf()`     | Tìm vị trí xuất hiện đầu tiên của một chuỗi con trong chuỗi gốc. | Phân biệt chữ hoa và chữ thường, trả về `-1` nếu không tìm thấy, hỗ trợ tham số `start`.        | Chỉ số của chuỗi con hoặc `-1`.         |
| `replace()`     | Thay thế một phần chuỗi bằng một chuỗi khác.                     | Thay thế lần đầu tiên tìm thấy.                                                                 | Chuỗi mới sau khi thay thế.             |
| `charAt()`      | Trả về ký tự tại một vị trí nhất định trong chuỗi.               | Nếu vị trí nằm ngoài phạm vi, trả về chuỗi rỗng.                                                | Ký tự tại chỉ số được chỉ định.         |

- substr()
- charCodeAt()
- lastIndexOf()
- repeat()

#### II. Array

**2.1. Array**

- Mảng có thể lưu trữ nhiều giá trị, các giá trị này có thể thuộc nhiều kiểu dữ liệu khác nhau. Mỗi giá trị trong mảng có một chỉ số và mỗi chỉ số được tham chiếu đến một địa chỉ trong bộ nhớ
- Mỗi giá trị có thể được truy cập bằng cách sử dụng chỉ số của chúng. Chỉ số của mảng bắt đầu từ 0, và chỉ số của phần tử cuối cùng sẽ nhỏ hơn một đơn vị so với độ dài của mảng.

- **Ví dụ:**

  ```
  const numbers = [0, 3.14, 9.81, 37, 98.6, 100] // array of numbers
  const fruits = ['banana', 'orange', 'mango', 'lemon'] // array of strings, fruits

  // Print the array and its length

  console.log('Numbers:', numbers)
  console.log('Number of numbers:', numbers.length)

  console.log('Fruits:', fruits)
  console.log('Number of fruits:', fruits.length)

  ```

  ```
  Numbers: [0, 3.14, 9.81, 37, 98.6, 100]
  Number of numbers: 6
  Fruits: ['banana', 'orange', 'mango', 'lemon']
  Number of fruits: 4
  ```

- Truy cập giá trị trong mảng bằng chỉ số

  ```js
  const webTechs = [
    "HTML",
    "CSS",
    "JavaScript",
    "React",
    "Redux",
    "Node",
    "MongoDB",
  ]; // List of web technologies

  console.log(webTechs); // all the array items
  console.log(webTechs.length); // => to know the size of the array, which is 7
  console.log(webTechs[0]); //  -> HTML
  console.log(webTechs[6]); //  -> MongoDB

  let lastIndex = webTechs.length - 1;
  console.log(webTechs[lastIndex]); // -> MongoDB
  ```

**2.2. Array methods**

**1. length**

- Trả về một giá trị số nguyên đại diện cho số phần tử trong mảng.
- Là thuộc tính, không phải phương thức.
- **Cú pháp**:

  ```js
  array.length;
  ```

- **Ví dụ**:
  ```javascript
  const arr = [1, 2, 3, 4];
  console.log(arr.length); // 4
  ```

**2. push()**

- Thêm một hoặc nhiều phần tử vào cuối mảng.
- Thay đổi mảng ban đầu, trả về độ dài mới của mảng sau khi thêm phần tử.
- **Cú pháp**:

  ```js
  array.push(element1, element2, ..., elementN)
  ```

  - `element1, element2, ..., elementN`: Các phần tử cần thêm vào mảng.

- **Ví dụ**:
  ```javascript
  const arr = [1, 2];
  arr.push(3, 4);
  console.log(arr); // [1, 2, 3, 4]
  ```

**3. pop()**

- **Mục đích**: Loại bỏ phần tử cuối cùng khỏi mảng.
- **Đặc điểm, kết quả trả về**: Thay đổi mảng ban đầu, trả về phần tử bị loại bỏ.
- **Cú pháp**: `array.pop()`
  - **Tham số**: Không có.
- **Ví dụ**:
  ```javascript
  const arr = [1, 2, 3];
  const lastElement = arr.pop();
  console.log(arr); // [1, 2]
  console.log(lastElement); // 3
  ```

**4. splice()**

- Thêm, xóa hoặc thay thế các phần tử trong mảng.
- Thay đổi mảng ban đầu, trả về mảng chứa các phần tử đã bị xóa.
- **Cú pháp**:

  ```js
  array.splice(start, deleteCount, item1, item2, ..., itemN)
  ```

  - `start`: Vị trí bắt đầu thay đổi mảng.
  - `deleteCount`: Số phần tử cần xóa.
  - `item1, item2, ..., itemN`: Các phần tử cần thêm vào mảng.

- **Ví dụ**:
  ```javascript
  const arr = [1, 2, 3, 4];
  arr.splice(1, 2, 5, 6); // Xóa 2 phần tử từ vị trí 1, thêm 5 và 6
  console.log(arr); // [1, 5, 6, 4]
  ```

**5. slice()**

- Trích xuất một phần của mảng
- Không thay đổi mảng ban đầu, trả về mảng mới chứa phần tử từ chỉ số `begin` đến `end`.
- **Cú pháp**:
  ```js
  array.slice(begin, end);
  ```
  - `begin`: Chỉ số bắt đầu (chỉ số bắt đầu tính từ 0).
  - `end`: Chỉ số kết thúc (không bao gồm chỉ số này).
- **Ví dụ**:
  ```javascript
  const arr = [1, 2, 3, 4];
  const newArr = arr.slice(1, 3); // Trích xuất từ vị trí 1 đến 3 (không bao gồm 3)
  console.log(newArr); // [2, 3]
  ```

**6. indexOf()**

- Tìm vị trí của phần tử trong mảng.
- Trả về chỉ số của phần tử đầu tiên tìm thấy, nếu không tìm thấy trả về `-1`.
- **Cú pháp**:
  ```js
  array.indexOf(searchElement, fromIndex);
  ```
  - `searchElement`: Phần tử cần tìm.
  - `fromIndex`: Vị trí bắt đầu tìm kiếm (tùy chọn).
- **Ví dụ**:
  ```javascript
  const arr = [1, 2, 3, 4];
  console.log(arr.indexOf(3)); // 2
  console.log(arr.indexOf(5)); // -1
  ```

**7. concat()**

- Nối hai hoặc nhiều mảng lại với nhau và trả về mảng mới.
- Không thay đổi mảng ban đầu, trả về mảng mới chứa các phần tử được nối.
- **Cú pháp**:

  ```js
  array.concat(value1, value2, ..., valueN)
  ```

  - `value1, value2, ..., valueN`: Các mảng hoặc giá trị cần nối vào mảng ban đầu.

- **Ví dụ**:
  ```javascript
  const arr1 = [1, 2];
  const arr2 = [3, 4];
  const newArr = arr1.concat(arr2);
  console.log(newArr); // [1, 2, 3, 4]
  ```

**8. includes()**

- Kiểm tra xem mảng có chứa phần tử cụ thể không.
- Trả về `true` nếu mảng chứa phần tử, ngược lại trả về `false`.
- **Cú pháp**:
  ```js
  array.includes(element, fromIndex);
  ```
  - `element`: Phần tử cần kiểm tra.
  - `fromIndex`: Vị trí bắt đầu kiểm tra (tùy chọn).
- **Ví dụ**:
  ```javascript
  const arr = [1, 2, 3];
  console.log(arr.includes(2)); // true
  console.log(arr.includes(4)); // false
  ```

**9. join()**

- Kết hợp tất cả các phần tử trong mảng thành một chuỗi.
- Không thay đổi mảng ban đầu, trả về một chuỗi với các phần tử được nối bằng ký tự phân cách.
- **Cú pháp**:
  ```js
  array.join(separator);
  ```
  - `separator`: Ký tự phân cách các phần tử trong chuỗi (tùy chọn, mặc định là dấu phẩy).
- **Ví dụ**:
  ```javascript
  const arr = ["apple", "banana", "cherry"];
  console.log(arr.join(", ")); // "apple, banana, cherry"
  ```

**10. reverse()**

- Đảo ngược thứ tự các phần tử trong mảng.
- Thay đổi mảng ban đầu, trả về mảng đã đảo ngược.
- **Cú pháp**:
  ```js
  array.reverse();
  ```
- **Ví dụ**:

  ```javascript
  const arr = [1, 2, 3];
  console.log(arr.reverse()); // [3, 2, 1]
  ```

**11. sort()**

- Sắp xếp các phần tử trong mảng theo thứ tự.
- Thay đổi mảng ban đầu, trả về mảng đã được sắp xếp.
- **Cú pháp**:
  ```js
  array.sort(compareFunction);
  ```
  - `compareFunction`: Hàm so sánh tùy chọn để xác định thứ tự (nếu không có, mảng sẽ được sắp xếp theo thứ tự chuỗi mặc định).
- **Ví dụ**:
  ```javascript
  const arr = [4, 2, 3, 1];
  arr.sort((a, b) => a - b); // Sắp xếp theo thứ tự tăng dần
  console.log(arr); // [1, 2, 3, 4]
  ```

**12. shift()**

- Loại bỏ phần tử đầu tiên khỏi mảng.
- Thay đổi mảng ban đầu, trả về phần tử bị loại bỏ.
- **Cú pháp**:
  ```js
  array.shift();
  ```
- **Ví dụ**:
  ```javascript
  const arr = [1, 2, 3];
  console.log(arr.shift()); // 1
  console.log(arr); // [2, 3]
  ```

**13. unshift()**

- Thêm một hoặc nhiều phần tử vào đầu mảng.
- Thay đổi mảng ban đầu, trả về mảng mới
- **Cú pháp**:
  ```js
  array.unshift(element1, element2, ..., elementN)
  ```
  - `element1, element2, ..., elementN`: Các phần tử cần thêm vào đầu mảng.
- **Ví dụ**:

  ```javascript
  const arr = [2, 3];
  arr.unshift(1);
  console.log(arr); // [1, 2, 3]
  ```

**14. Bảng mô tả các phương thức mảng**

| **Phương thức** | **Mục đích**                                     | **Đặc điểm**                                                   | **Kết quả trả về**                                       |
| --------------- | ------------------------------------------------ | -------------------------------------------------------------- | -------------------------------------------------------- |
| `length`        | Trả về số lượng phần tử trong mảng.              | Là thuộc tính, không phải phương thức.                         | Giá trị số nguyên, là số phần tử trong mảng.             |
| `push()`        | Thêm một hoặc nhiều phần tử vào cuối mảng.       | Thay đổi mảng ban đầu.                                         | Độ dài mới của mảng.                                     |
| `pop()`         | Loại bỏ phần tử cuối cùng khỏi mảng.             | Thay đổi mảng ban đầu.                                         | Phần tử bị loại bỏ.                                      |
| `splice()`      | Thêm, xóa hoặc thay thế phần tử trong mảng.      | Thay đổi mảng ban đầu.                                         | Mảng chứa các phần tử bị xóa.                            |
| `slice()`       | Trích xuất một phần của mảng và trả về mảng mới. | Không thay đổi mảng ban đầu.                                   | Mảng mới chứa các phần tử được trích xuất.               |
| `indexOf()`     | Tìm vị trí của phần tử trong mảng.               | Tìm phần tử đầu tiên, trả về -1 nếu không tìm thấy.            | Chỉ số của phần tử đầu tiên, hoặc -1 nếu không tìm thấy. |
| `concat()`      | Nối các mảng hoặc giá trị lại với nhau.          | Không thay đổi mảng ban đầu.                                   | Mảng mới chứa các phần tử đã nối.                        |
| `includes()`    | Kiểm tra xem mảng có chứa phần tử cụ thể không.  | Trả về `true` nếu mảng chứa phần tử, ngược lại trả về `false`. | `true` hoặc `false`.                                     |
| `join()`        | Kết hợp các phần tử trong mảng thành một chuỗi.  | Không thay đổi mảng ban đầu.                                   | Một chuỗi các phần tử nối với nhau.                      |
| `reverse()`     | Đảo ngược thứ tự các phần tử trong mảng.         | Thay đổi mảng ban đầu.                                         | Mảng đã đảo ngược.                                       |
| `sort()`        | Sắp xếp các phần tử trong mảng.                  | Thay đổi mảng ban đầu.                                         | Mảng đã được sắp xếp.                                    |
| `shift()`       | Loại bỏ phần tử đầu tiên khỏi mảng.              | Thay đổi mảng ban đầu.                                         | Phần tử bị loại bỏ.                                      |
| `unshift()`     | Thêm một hoặc nhiều phần tử vào đầu mảng.        | Thay đổi mảng ban đầu.                                         | Độ dài mới của mảng.                                     |

#### III. Object

**1. Object là gì?**

- Object hay đối tượng trong JS là tập hợp các cặp **key-value**. Và **property** là tên gọi của mỗi cặp **key-value**
- **Giá trị (value)** của một **property** có thể thuộc bất kỳ kiểu dữ liệu như: string, number, object hay function
- **Đặc điểm**: Object trong JavaScript là thay đổi được (mutable) và không có thứ tự nhất định trong các phần tử.

  ```javascript
  const empty = {};

  const person = {
    name: "John",
    age: 30,
    isStudent: false,
  };
  ```

**2. Tạo phương thức trong Object**

- Tạo một hàm bên trong một object để thực hiện hành động liên quan đến object đó.
- Phương thức trong object có thể thực thi các hành động hoặc trả về giá trị.

  ```javascript
  const person = {
    name: "John",
    greet: function () {
      console.log("Hello, " + this.name);
    },
  };
  person.greet(); // Output: Hello, John
  ```

- Để truy cập property name method greet thì ta sử dụng keyword **`this`**.
- Keyword **`this`** tham chiếu đến object person. Do đó, ta có thể truy cập **property** của object thông qua **`this`**

**3. Truy cập giá trị trong Object**

- Truy cập và lấy giá trị của một thuộc tính trong Object qua `dot notation` hoặc `bracket notation`.

  - Dot notation: `object.key`
  - Bracket notation: `object["key"]`

- **Ví dụ**:

  ```javascript
  const person = { name: "John", age: 30 };
  console.log(person.name); // John
  console.log(person["age"]); // 30
  ```

**4. Tạo key mới trong Object**

- Thêm mới hoặc cập nhật giá trị cho một key trong object.
- Key có thể được thêm bằng cách sử dụng `dot notation` hoặc `bracket notation`

  - `object.key = value;`
  - `object["key"] = value;`

- **Ví dụ**:

  ```javascript
  const person = { name: "John" };
  person.age = 30; // Thêm key mới
  person["isStudent"] = true; // Thêm key mới
  console.log(person); // { name: 'John', age: 30, isStudent: true }
  ```

**5. Object Methods**

**1. Object.assign()**

- Sao chép tất cả các thuộc tính từ một hoặc nhiều đối tượng nguồn vào đối tượng đích.
- Phương thức này thay đổi đối tượng mới và trả về đối tượng mới.

- **Cú pháp**:

  ```javascript
  Object.assign(target, sources);
  ```

- **Ví dụ**:

  ```javascript
  const person = { name: "John" };
  const details = { age: 30, country: "USA" };
  const mergedPerson = Object.assign({}, person, details);
  console.log(mergedPerson); // { name: 'John', age: 30, country: 'USA' }
  ```

**2. Object.keys()**

- Trả về một mảng chứa tất cả các keys của đối tượng.
- Các keys được trả về trong một mảng và theo thứ tự của Object.

- **Cú pháp**:

  ```javascript
  Object.keys(object);
  ```

- **Ví dụ**:

  ```javascript
  const person = { name: "John", age: 30 };
  console.log(Object.keys(person)); // ['name', 'age']
  ```

**3. Object.values()**

- Trả về một mảng chứa tất cả các giá trị (values) của các thuộc tính trong đối tượng.

- **Cú pháp**:

  ```javascript
  Object.values(object);
  ```

- **Ví dụ**:

  ```javascript
  const person = { name: "John", age: 30 };
  console.log(Object.values(person)); // ['John', 30]
  ```

**4. Object.entries()**

- Trả về một mảng chứa các cặp key-value trong Object dưới dạng mảng con.
- Các cặp key-value được trả về dưới dạng mảng của mảng con.

- **Cú pháp**:

  ```javascript
  Object.entries(object);
  ```

- **Ví dụ**:

  ```javascript
  const person = { name: "John", age: 30 };
  console.log(Object.entries(person)); // [['name', 'John'], ['age', 30]]
  ```

**5. hasOwnProperty()**

- Kiểm tra xem object có thuộc tính (key) nhất định không, và thuộc tính đó có phải là của chính object đó (không phải kế thừa từ prototype).
- Trả về `true` nếu object có thuộc tính đó, `false` nếu không có.

- **Cú pháp**:

  ```javascript
  object.hasOwnProperty(key);
  ```

- **Ví dụ**:

  ```javascript
  const person = { name: "John", age: 30 };
  console.log(person.hasOwnProperty("name")); // true
  console.log(person.hasOwnProperty("gender")); // false
  ```

**6. Bảng mô tả các phương thức đối tượng**

| **Phương thức**      | **Mục đích**                                                              | **Kết quả trả về**                                                       |
| -------------------- | ------------------------------------------------------------------------- | ------------------------------------------------------------------------ |
| **Object.assign()**  | Sao chép thuộc tính từ một hoặc nhiều đối tượng nguồn vào đối tượng đích. | Trả về đối tượng đích sau khi gộp tất cả thuộc tính từ các object nguồn. |
| **Object.keys()**    | Lấy tất cả các key của object dưới dạng mảng.                             | Một mảng chứa tất cả các key của object.                                 |
| **Object.values()**  | Lấy tất cả các giá trị (values) của object dưới dạng mảng.                | Một mảng chứa tất cả các giá trị của object.                             |
| **Object.entries()** | Lấy tất cả các cặp key-value của object dưới dạng mảng của mảng con.      | Một mảng chứa các cặp key-value dưới dạng mảng con.                      |
| **hasOwnProperty()** | Kiểm tra xem object có thuộc tính được chỉ định hay không.                | `true` nếu thuộc tính tồn tại trong object, `false` nếu không tồn tại.   |
