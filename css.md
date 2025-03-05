/* Для мобильных устройств */
@media (max-width: 480px) {
    form {
        padding: 15px;
    }
    
    .checkbox-group label {
        font-size: 0.85rem;
    }
    
    button[type="submit"] {
        width: 100%;
    }
}

/* Визуальная обратная связь */
input:focus, button:focus {
    outline: 2px solid #ff69b4;
    outline-offset: 2px;
}
