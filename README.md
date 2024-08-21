# 📝 React Custom Form with Zod Validation

This repository contains an example of a custom form in React using `react-hook-form` and `zod` for data validation. The form includes fields for name, email, password, and password confirmation, all validated according to a schema defined with `zod`.

## 🚀 Technologies Used

- **React**: JavaScript library for building user interfaces.
- **React Hook Form**: Library for managing forms in React simply and flexibly.
- **Zod**: Library for schema-based data validation.

- **TypeScript**: A superset of JavaScript that adds static types to the language.

## 📂 Project Structure


```bash
src/
│

├── components/
│   ├── CustomForm/
│   │   └── CustomForm.tsx   # Main form component
│   └── CustomInput/
│       └── CustomInput.tsx  # Reusable component for form fields
│
├── models/
│   └── index.ts             # Type definitions and validation schema with Zod
│
├── App.tsx                  # Main application component
├── index.tsx                # React entry point
└── App.css                  # General application styles
```

## 🛠️ Installation

1. Clone the repository:
   ```bash

   git clone https://github.com/your-username/repo-name.git
   cd repo-name
   ```

2. Install dependencies:
   ```bash
   npm install
   ```

3. Run the application:
   ```bash
   npm start
   ```


## 📜 Usage

This project provides a solid base for creating forms in React with robust validation. The modular structure allows you to easily add new fields and validations.

### Customization

You can modify the validation schema in `src/models/index.ts` to suit the needs of your form.

### Example Schema with Zod

```typescript
import * as z from "zod";

export const schema = z.object({
  name: z.string().min(1, "Name is required"),
  email: z.string().email("Must be a valid email"),
  password: z.string().min(8, "Password must be at least 8 characters long"),
  confirmPassword: z.string().min(8, "You must confirm your password")
    .refine((val, ctx) => val === ctx.parent.password, {
      message: "Passwords must match",
    }),
});


export type FormValues = z.infer<typeof schema>;

```


## 🤝 Contributions

Contributions are welcome! If you have any improvements or find any bugs, feel free to open an issue or submit a pull request.


## 📝 License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for more details.
